Ansible September
=========

This role deploy the September Gemini-to-HTTP proxy (https://github.com/gemrest/september) on x86 or ARM Linux computers.

Requirements
------------

None

Role Variables
--------------

Available variables are listed below, along with default values (see `defaults/main.yml`):
```yaml
proxy_port: 80
proxy_gemini_domain: ""
september_css: ""
```
- `proxy_port`: Default value 80. Port on which the http proxy will listen
- `proxy_gemini_domain`: No default value. The Gemini capsule to serve through the proxy. Do not include `gemini://` in the path. 
- `september_css`: No default value. The CSS to apply when rendering your Gemini capsule through the proxy.

Dependencies
------------

None

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: all
      roles:
         - { role: vinibo.september, gemini_domain: "geminispace.info" }

Notes
-----
The September binaries are compiled on my own computer, using the `-r` flag and using `cross` for targeting other architectures.

- armv7: `cross build -r --target arm-unknown-linux-gnueabihf`
- aarch64: `cross build -r --target aarch64-unknown-linux-gnu`
- riscv: `cross build -r --target riscv64gc-unknown-linux-gnu`

License
-------

MIT

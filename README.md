ansible-role-win10-languagepack
=========

Add language packs to a Windows 10 multi-session.   
According to: [https://docs.microsoft.com/en-us/azure/virtual-desktop/language-packs](https://docs.microsoft.com/en-us/azure/virtual-desktop/language-packs)


Role Variables
--------------
The default values for the variables are set in `defaults/main.yml`:

```yaml
language_experience_pack_download_dir: 'C:\temp'
language_experience_pack_isos:
  - url: 'https://software-download.microsoft.com/download/pr/19041.1.191206-1406.vb_release_CLIENTLANGPACKDVD_OEM_MULTI.iso'
    dest: '{{ language_experience_pack_download_dir }}\langpack.iso'
  - url: 'https://software-download.microsoft.com/download/pr/19041.1.191206-1406.vb_release_amd64fre_FOD-PACKAGES_OEM_PT1_amd64fre_MULTI.iso'
    dest: '{{ language_experience_pack_download_dir }}\fod.iso'
  - url: 'https://software-download.microsoft.com/download/sg/19041.928.210407-2138.vb_release_svc_prod1_amd64fre_InboxApps.iso'
    dest: '{{ language_experience_pack_download_dir }}\inboxapps.iso'

language_experience_packs:
  - de-de

language_experience_pack_isos_remove_when_finished: true
```

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```yaml
- hosts: win10multi
  vars:
    language_experience_pack_download_dir: 'D:\temp'
    language_experience_packs:
      - de-de
      - nl-nl

  roles:
    - { role: ansible-role-win10-languagepack }
```

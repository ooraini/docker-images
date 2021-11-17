# Rocky Linux Docker Images

Forked from [AlmaLinux Docker images](https://github.com/AlmaLinux/docker-images).

## Build Requirements

```
vagrant
vagrant-libvirt
ansible (Most versions will probably work)
```

## Build
### Ansible Varibles

```
clean_start: false # Clears the build directory and starts over everytime
git_repo: https://github.com/ooraini/docker-images # Repository to pull from
build_dir: /root/docker-images
arch: x86_64
registry_url: docker.io
registry_org: omaraloraini
registry_user: omaraloraini
image_name_prefix: 'rockylinux-' # Final image name: "${registry_url}/${registry_org}/${image_name_prefix}8-${tag}"
image_variants:
  - minimal
  - base
  - init
  - micro      
image_tags:
  - 8
  - 8.5
enalbe_image_push: yes # Will attempt to push images to the registry
```

### Commands

`vagrant up`

`ansible-playbook -i 192.168.33.10, playbook.yml -u vagrant`

## References

* Docker documentaion - [Create a base image](https://docs.docker.com/develop/develop-images/baseimages/)
* Opencontainers [image-spec annotations/labels](https://github.com/opencontainers/image-spec/blob/master/annotations.md)
* RedHat [Kickstart Reference guide](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/8/html/system_design_guide/kickstart-script-file-format-reference_system-design-guide)

## License

Licensed under the MIT license, see the [LICENSE](LICENSE) file for details.

[![CI](https://github.com/de-it-krachten/ansible-role-epel/workflows/CI/badge.svg?event=push)](https://github.com/de-it-krachten/ansible-role-epel/actions?query=workflow%3ACI)


# ansible-role-epel

EPEL 


## Platforms

Supported platforms

- Red Hat Enterprise Linux 7<sup>1</sup>
- Red Hat Enterprise Linux 8<sup>1</sup>
- Red Hat Enterprise Linux 9<sup>1</sup>
- CentOS 7
- CentOS 8
- RockyLinux 8
- OracleLinux 8
- AlmaLinux 8
- AlmaLinux 9

Note:
<sup>1</sup> : no automated testing is performed on these platforms

## Role Variables
### defaults/main.yml
<pre><code>
# EPEL rpm url
epel_package: https://dl.fedoraproject.org/pub/epel/epel-release-latest-{{ ansible_distribution_major_version }}.noarch.rpm

# EPEL GPG download location
epel_gpgkey: https://dl.fedoraproject.org/pub/epel/RPM-GPG-KEY-EPEL-{{ ansible_distribution_major_version }}

# Mode to operate in
epel_mode: enabled
</pre></code>

### vars/RedHat-8.yml
<pre><code>
# List of satellite repositories to enable
satellite_repositories:
  - "codeready-builder-for-rhel-8-x86_64-rpms"
</pre></code>

### vars/default.yml
<pre><code>

</pre></code>

### vars/RedHat-9.yml
<pre><code>
# List of satellite repositories to enable
satellite_repositories:
  - "codeready-builder-for-rhel-9-x86_64-rpms"
</pre></code>

### vars/RedHat-7.yml
<pre><code>
# List of satellite repositories to enable
satellite_repositories:
  - "rhel-*-optional-rpms"
  - "rhel-*-extras-rpms"
  - "rhel-ha-for-rhel-*-server-rpms"
</pre></code>

### vars/OracleLinux.yml
<pre><code>
# OracleLinux RPM
epel_package: oracle-epel-release-el{{ ansible_distribution_major_version }}
</pre></code>



## Example Playbook
### molecule/default/converge.yml
<pre><code>
- name: sample playbook for role 'epel'
  hosts: all
  vars:
  pre_tasks:
    - name: Create 'remote_tmp'
      file:
        path: /root/.ansible/tmp
        state: directory
        mode: "0700"

  tasks:
    # - name: Include role 'rhsm'
    #   include_role:
    #     name: rhsm
    #   when:
    #     - ansible_distribution == 'RedHat'
    #     - ansible_distribution_major_version == '8'

    - name: Include role 'epel'
      include_role:
        name: epel
</pre></code>

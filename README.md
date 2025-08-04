[![CI](https://github.com/de-it-krachten/ansible-role-epel/workflows/CI/badge.svg?event=push)](https://github.com/de-it-krachten/ansible-role-epel/actions?query=workflow%3ACI)


# ansible-role-epel

Installs and activates EPEL on a variety of RedHat flavors 



## Dependencies

#### Roles
- deitkrachten.facts

#### Collections
None

## Platforms

Supported platforms

- Red Hat Enterprise Linux 8
- Red Hat Enterprise Linux 9
- Red Hat Enterprise Linux 10
- CentOS Stream 9
- CentOS Stream 10
- RockyLinux 8
- RockyLinux 9
- RockyLinux 10
- OracleLinux 8
- OracleLinux 9
- OracleLinux 10
- AlmaLinux 8
- AlmaLinux 9
- AlmaLinux 10

Note:
<sup>1</sup> : no automated testing is performed on these platforms

## Role Variables
### defaults/main.yml
<pre><code>
# list of default satellite repostories to enable
epel_satellite_repositories_default: []

# list of epel satellite repostories to disable
epel_satellite_repositories_epel: []

# Mode to operate in
epel_state: enabled


# ----------------------------------------------------------------
# EPEL mode 'public'
# ----------------------------------------------------------------

# EPEL mode
epel_mode: public

# EPEL rpm url
epel_rpm_package: https://dl.fedoraproject.org/pub/epel/epel-release-latest-{{ ansible_distribution_major_version }}.noarch.rpm

# EPEL GPG download location
epel_gpgkey_url: https://dl.fedoraproject.org/pub/epel/RPM-GPG-KEY-EPEL-{{ ansible_distribution_major_version }}

# Location of GPG key on disk
epel_gpgkey_file: /etc/pki/rpm-gpg/RPM-GPG-KEY-EPEL-{{ ansible_distribution_major_version }}


# ----------------------------------------------------------------
# EPEL mode 'private'
# ----------------------------------------------------------------

# EPEL mode
# epel_mode: private

# EPEL repo name
epel_repo_name: epel

# EPEL repository description
epel_repo_description: epel

# EPEL repository url
# epel_repo_url: https://www.example.com/epel
</pre></code>

### defaults/CentOS-7.yml
<pre><code>
# List of EPEL packages
epel_packages:
  - epel-release
</pre></code>

### defaults/CentOS-8.yml
<pre><code>
# List of EPEL packages
epel_packages:
  - epel-release
</pre></code>

### defaults/CentOS-Stream-8.yml
<pre><code>
# List of EPEL packages
epel_packages:
  - epel-release
  - epel-next-release
</pre></code>

### defaults/CentOS-Stream-9.yml
<pre><code>
# List of EPEL packages
epel_packages:
  - epel-release
  - epel-next-release
</pre></code>

### defaults/default.yml
<pre><code>

</pre></code>

### defaults/OracleLinux.yml
<pre><code>
# OracleLinux RPM
epel_packages:
  - oracle-epel-release-el{{ ansible_distribution_major_version }}
</pre></code>

### defaults/RedHat-7.yml
<pre><code>
# List of satellite repositories to enable
epel_satellite_repositories_default:
  - rhel-7-server-extras-rpms
  - rhel-7-server-optional-rpms
  - rhel-ha-for-rhel-7-server-rpms
</pre></code>

### defaults/RedHat-8.yml
<pre><code>
# List of satellite repositories to enable
epel_satellite_repositories_default:
  - codeready-builder-for-rhel-8-x86_64-rpms
</pre></code>

### defaults/RedHat-9.yml
<pre><code>
# List of satellite repositories to enable
epel_satellite_repositories_default:
  - codeready-builder-for-rhel-9-x86_64-rpms
</pre></code>




## Example Playbook
### molecule/default/converge.yml
<pre><code>
- name: sample playbook for role 'epel'
  hosts: all
  become: 'yes'
  roles:
    - deitkrachten.facts
  tasks:
    - name: Include role 'epel'
      ansible.builtin.include_role:
        name: epel
</pre></code>

[![CI](https://github.com/de-it-krachten/ansible-role-epel/workflows/CI/badge.svg?event=push)](https://github.com/de-it-krachten/ansible-role-epel/actions?query=workflow%3ACI)


# ansible-role-epel

Installs and activates EPEL on a variety of RedHat flavors 


## Platforms

Supported platforms

- Red Hat Enterprise Linux 7
- Red Hat Enterprise Linux 8
- Red Hat Enterprise Linux 9
- CentOS 7
- CentOS 8
- CentOS Stream 8
- CentOS Stream 9
- RockyLinux 8
- RockyLinux 9
- OracleLinux 8
- AlmaLinux 8
- AlmaLinux 9

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
epel_packages:
  - https://dl.fedoraproject.org/pub/epel/epel-release-latest-{{ ansible_distribution_major_version }}.noarch.rpm

# EPEL GPG download location
epel_gpgkey: https://dl.fedoraproject.org/pub/epel/RPM-GPG-KEY-EPEL-{{ ansible_distribution_major_version }}


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

### vars/RedHat-8.yml
<pre><code>
# List of satellite repositories to enable
epel_satellite_repositories_default:
  - codeready-builder-for-rhel-8-x86_64-rpms
</pre></code>

### vars/CentOS-Stream-8.yml
<pre><code>
# List of EPEL packages
epel_packages:
  - epel-release
  - epel-next-release
</pre></code>

### vars/default.yml
<pre><code>

</pre></code>

### vars/CentOS-8.yml
<pre><code>
# List of EPEL packages
epel_packages:
  - epel-release
</pre></code>

### vars/RedHat-9.yml
<pre><code>
# List of satellite repositories to enable
epel_satellite_repositories_default:
  - codeready-builder-for-rhel-9-x86_64-rpms
</pre></code>

### vars/RedHat-7.yml
<pre><code>
# List of satellite repositories to enable
epel_satellite_repositories_default:
  - rhel-7-server-extras-rpms
  - rhel-7-server-optional-rpms
  - rhel-ha-for-rhel-7-server-rpms
</pre></code>

### vars/OracleLinux.yml
<pre><code>
# OracleLinux RPM
epel_packages:
  - oracle-epel-release-el{{ ansible_distribution_major_version }}
</pre></code>

### vars/CentOS-7.yml
<pre><code>
# List of EPEL packages
epel_packages:
  - epel-release
</pre></code>

### vars/CentOS-Stream-9.yml
<pre><code>
# List of EPEL packages
epel_packages:
  - epel-release
  - epel-next-release
</pre></code>



## Example Playbook
### molecule/default/converge.yml
<pre><code>
- name: sample playbook for role 'epel'
  hosts: all
  become: "{{ molecule['converge']['become'] | default('yes') }}"
  tasks:
    - name: Include role 'epel'
      include_role:
        name: epel
</pre></code>

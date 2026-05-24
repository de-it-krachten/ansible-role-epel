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
# Mode to operate in
epel_state: enabled

# ----------------------------------------------------------------
# EPEL mode 'public'
# ----------------------------------------------------------------

# EPEL mode
epel_mode: public

# EPEL rpm url
epel_rpm_package: https://dl.fedoraproject.org/pub/epel/epel-release-latest-{{ ansible_facts.distribution_major_version }}.noarch.rpm

# EPEL GPG download location
epel_gpgkey_url: https://dl.fedoraproject.org/pub/epel/RPM-GPG-KEY-EPEL-{{ ansible_facts.distribution_major_version }}

# Location of GPG key on disk
epel_gpgkey_file: /etc/pki/rpm-gpg/RPM-GPG-KEY-EPEL-{{ ansible_facts.distribution_major_version }}


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

# ----------------------------------------------------------------
# OS Specific defaults
# ----------------------------------------------------------------

# OS-oriented defaults
__epel_os_defaults:
  default:
    epel_packages:
      - epel-release
    epel_satellite_repositories_default: []
    epel_satellite_repositories_epel: []
  'RedHat':
    epel_packages: []
  'RedHat-7':
    # List of satellite repositories to enable
    epel_satellite_repositories_default:
      - rhel-7-server-extras-rpms
      - rhel-7-server-optional-rpms
      - rhel-ha-for-rhel-7-server-rpms
  'RedHat-8':
    # List of satellite repositories to enable
    epel_satellite_repositories_default:
      - codeready-builder-for-rhel-8-x86_64-rpms
  'RedHat-9':
    # List of satellite repositories to enable
    epel_satellite_repositories_default:
      - codeready-builder-for-rhel-9-x86_64-rpms
  'RedHat-10':
    # List of satellite repositories to enable
    epel_satellite_repositories_default:
      - codeready-builder-for-rhel-10-x86_64-rpms

# OS key helpers
__epel_distro: "{{ ansible_facts.distribution }}"
__epel_os_family: "{{ ansible_facts.os_family }}"
__epel_distro_version: "{{ __epel_distro }}-{{ ansible_facts.distribution_major_version }}"
__epel_os_version: "{{ __epel_os_family }}-{{ ansible_facts.distribution_major_version }}"

# Construct defaults in the corrct order
__epel_os: >-
  {{
    __epel_os_defaults['default'] | default({}) |
    combine(__epel_os_defaults['family-'+__epel_os_family] | default({})) |
    combine(__epel_os_defaults['family-'+__epel_os_version] | default({})) |
    combine(__epel_os_defaults[__epel_distro] | default({})) |
    combine(__epel_os_defaults[__epel_distro_version] | default({}))
  }}

# Public variables — all lazy, all overridable
epel_packages: "{{ __epel_os.epel_packages }}"
epel_satellite_repositories_default: "{{ __epel_os.epel_satellite_repositories_default }}"
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
- name: sample playbook for role 'epel' post playbook
  ansible.builtin.import_playbook: converge-post.yml
  when: molecule_converge_post is undefined or molecule_converge_post | bool
</pre></code>

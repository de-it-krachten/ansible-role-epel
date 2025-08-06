# [1.10.0](https://github.com/de-it-krachten/ansible-role-epel/compare/v1.9.1...v1.10.0) (2025-08-06)


### Features

* Add support for AlmaLinux 10 ([f1c0ee3](https://github.com/de-it-krachten/ansible-role-epel/commit/f1c0ee33bfc2210536e90397e838120c80ec042f))
* Add support for CentOS Stream 10 ([a479ce5](https://github.com/de-it-krachten/ansible-role-epel/commit/a479ce503724f4259de10ce2b53c154dd6c51107))
* Add support for OracleLinux 10 ([8269bed](https://github.com/de-it-krachten/ansible-role-epel/commit/8269bedea5071de37a8203e7ab6aa3a966d2bee1))
* Add support for Red Hat Enterprise Linux 10 ([dc35727](https://github.com/de-it-krachten/ansible-role-epel/commit/dc35727846caa87b8b53c28c44c1301eff6c9f3b))
* Add support for RockyLinux 10 ([95313d3](https://github.com/de-it-krachten/ansible-role-epel/commit/95313d367d9eaf3af80da024bb07484b4734a6cb))

## [1.9.1](https://github.com/de-it-krachten/ansible-role-epel/compare/v1.9.0...v1.9.1) (2025-08-04)


### Bug Fixes

* Delete unwanted '.ansible' files making 'ansible-galaxy' fail ([9df5a6d](https://github.com/de-it-krachten/ansible-role-epel/commit/9df5a6d4b3e6d2df1b8fe5d9e7eb5bde1a030fb8))

# [1.9.0](https://github.com/de-it-krachten/ansible-role-epel/compare/v1.8.0...v1.9.0) (2024-12-29)


### Features

* Update supported platforms & CI ([107f680](https://github.com/de-it-krachten/ansible-role-epel/commit/107f680363e33a2960f4cd58d308810327fbc67f))

# [1.8.0](https://github.com/de-it-krachten/ansible-role-epel/compare/v1.7.2...v1.8.0) (2024-06-10)


### Features

* Add support for Ubuntu 24.04 LTS + Fedora 40 ([1561ccb](https://github.com/de-it-krachten/ansible-role-epel/commit/1561ccbd2960e3f6fd4cb70c4e7b1c1327d649ac))

## [1.7.2](https://github.com/de-it-krachten/ansible-role-epel/compare/v1.7.1...v1.7.2) (2024-04-10)


### Bug Fixes

* Add method of disabling repo ([c55bc6f](https://github.com/de-it-krachten/ansible-role-epel/commit/c55bc6fae0f8030150641e82365361b2bcb9a528))
* Make it possible to disable EPEL ([13daf2e](https://github.com/de-it-krachten/ansible-role-epel/commit/13daf2edfc581cc9a4eaf689423217155f0bbf86))
* Remove execution of external role 'facts' ([7a31726](https://github.com/de-it-krachten/ansible-role-epel/commit/7a31726cc9e722d135ac57791f4f8144f094b1a7))

## [1.7.1](https://github.com/de-it-krachten/ansible-role-epel/compare/v1.7.0...v1.7.1) (2023-09-09)


### Bug Fixes

* Move OS specific variables vars->defaults ([82b9f0b](https://github.com/de-it-krachten/ansible-role-epel/commit/82b9f0b313402e30f222c0f826df09148d05ea35))

# [1.7.0](https://github.com/de-it-krachten/ansible-role-epel/compare/v1.6.0...v1.7.0) (2023-08-30)


### Features

* Update supported platforms & CI ([0637207](https://github.com/de-it-krachten/ansible-role-epel/commit/0637207e014f9de295dbd14abd54c958dfe128f0))

# [1.6.0](https://github.com/de-it-krachten/ansible-role-epel/compare/v1.5.0...v1.6.0) (2023-01-12)


### Features

* Update CI/README/Platforms ([2121f71](https://github.com/de-it-krachten/ansible-role-epel/commit/2121f71eacd6a4b48e13e73d258b2ba0a0bdde3c))

# [1.5.0](https://github.com/de-it-krachten/ansible-role-epel/compare/v1.4.2...v1.5.0) (2022-10-12)


### Bug Fixes

* Move custom fact to 'ansible-role-facts' and set-up dependency ([087f55c](https://github.com/de-it-krachten/ansible-role-epel/commit/087f55c2dded386bd6f704515633a0a345119eff))


### Features

* Move to FQCN ([8b5e3d4](https://github.com/de-it-krachten/ansible-role-epel/commit/8b5e3d453f374ea9a4565f2544ae575b326348ca))
* Update CI to latest standards ([4b2d6ab](https://github.com/de-it-krachten/ansible-role-epel/commit/4b2d6abb1d7c2e7a90d20207ae314d77913b0dc0))

## [1.4.2](https://github.com/de-it-krachten/ansible-role-epel/compare/v1.4.1...v1.4.2) (2022-09-27)


### Bug Fixes

* Remove warning messages ([ad7f285](https://github.com/de-it-krachten/ansible-role-epel/commit/ad7f285430ae9f5b8c0ee5515f64542ab903a80a))

## [1.4.1](https://github.com/de-it-krachten/ansible-role-epel/compare/v1.4.0...v1.4.1) (2022-09-15)


### Bug Fixes

* Removed false changes on non-existant repositories ([c07164c](https://github.com/de-it-krachten/ansible-role-epel/commit/c07164c708e91273a32c1dd7260fb1f2741c6b67))

# [1.4.0](https://github.com/de-it-krachten/ansible-role-epel/compare/v1.3.0...v1.4.0) (2022-07-28)


### Features

* Add support for GPG key download via proxy ([1926685](https://github.com/de-it-krachten/ansible-role-epel/commit/192668542938e9b40666524f1a3cd98e1e2cc399))
* Add support for proxy download of RPM ([5b9ba55](https://github.com/de-it-krachten/ansible-role-epel/commit/5b9ba558ead9ac7fc34f3e2e0b8ba3ac9f732617))
* Implement ansible-lint v6 support ([b12896e](https://github.com/de-it-krachten/ansible-role-epel/commit/b12896ea3cc6809113710b117aa6f925afdac8a2))

# [1.3.0](https://github.com/de-it-krachten/ansible-role-epel/compare/v1.2.0...v1.3.0) (2022-07-20)


### Bug Fixes

* Reactivate CI ([42e61c5](https://github.com/de-it-krachten/ansible-role-epel/commit/42e61c581b7aa6091c794681050db41cb06551af))


### Features

* Add support for RockyLinux 9 + CentOS Stream 8/9 ([162550a](https://github.com/de-it-krachten/ansible-role-epel/commit/162550ad72b57643b18d108ddaf1fc3b86a6ff6a))

# [1.2.0](https://github.com/de-it-krachten/ansible-role-epel/compare/v1.1.0...v1.2.0) (2022-07-20)


### Features

* Add support for RockyLinux 9 + CentOS Stream 8/9 ([25d28ed](https://github.com/de-it-krachten/ansible-role-epel/commit/25d28eda382382612b5110d060f9846f85f13774))

# [1.1.0](https://github.com/de-it-krachten/ansible-role-epel/compare/v1.0.1...v1.1.0) (2022-07-14)


### Features

* add support for private EPEL repositories ([b6fb4dd](https://github.com/de-it-krachten/ansible-role-epel/commit/b6fb4dd4c2517ce60ff6b9e56be0464e8190297a))

## [1.0.1](https://github.com/de-it-krachten/ansible-role-epel/compare/v1.0.0...v1.0.1) (2022-06-30)


### Bug Fixes

* delete empty meta/requirements.yml as it gets galaxy stuck ([e70e789](https://github.com/de-it-krachten/ansible-role-epel/commit/e70e789777be174ad7bfced2d5a29cddaae978c3))

# 1.0.0 (2022-06-30)


### Features

* Initial release ([f76e86d](https://github.com/de-it-krachten/ansible-role-epel/commit/f76e86db87f184f2a4701d23b7832e417385647d))

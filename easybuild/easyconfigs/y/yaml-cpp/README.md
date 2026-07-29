# yaml-cpp technical documentation

-   [yaml-cpp on GitHub](https://github.com/jbeder/yaml-cpp)

    -   [GitHub releases](https://github.com/jbeder/yaml-cpp/releases)


## EasyBuild

-   [yaml-cpp in the EasyBuilders repository](https://github.com/easybuilders/easybuild-easyconfigs/tree/develop/easybuild/easyconfigs/y/yaml-cpp)

-   There is no support for yaml-cpp in the CSCS repository.


### Version 0.7.0 for cpeGNU 22.12

-   This is a direct port of the EasyBuilders recipe.


### Version 0.8.0 for CPE 24.03

-   Trivial port of the 0.7.0 recipe.

-   Added the license information in May 2025.

-   For 25.09, we needed to add `-DCMAKE_POLICY_VERSION_MINIMUM=3.5` to use CMake 4.
    We also switched to the new EasyConfig parameters.


### Version 0.9.0 for CPE 26.03

-   An almost trivial port of the 0.8.0 recipe for 25.09

-   This version is already compliant with CMake 4 so the `-DCMAKE_POLICY_VERSION_MINIMUM=3.5`
    is no longer needed.

-   We also added some additional sanity checks (on the pkg-config data).

-   Added testing with a built-in googletest (1.13.0, which is older than ours, switching
    to ours with an additional CMake flag did not work and does not make much sense either
    as there is no additional download required).


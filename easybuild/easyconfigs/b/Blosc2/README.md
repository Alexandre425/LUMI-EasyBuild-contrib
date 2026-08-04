# Blosc2 technical information

Installing Blosc2 turns out to be a painful affair and we're not sure the configuration is
optimal. It very much likes internal builds of the dependencies, but the consequences when
linking with other libraries that have been compiled with external versions, is not clear.

-   [Blosc website](https://blosc.org/)

-   [Blosc2 on GitHub](https://github.com/Blosc/c-blosc2)

    -   [GitHub releases](https://github.com/Blosc/c-blosc2/releases)


## EasyBuild

-   [Blosc2 support in the EasyBuilders repository](https://github.com/easybuilders/easybuild-easyconfigs/tree/develop/easybuild/easyconfigs/b/Blosc2)


### Version 3.2.3 for 26.03

-   We started from the EasyBuilders EasyConfig but it turned out that that was a very
    bad one as it downloaded lz4, zstd, zlib-ng and zfp in the background, all codes that
    we have.

-   Choice:

    -   Use external packages (which we choose)

    -   Put sources where Blosc2 an find them (there are CMake flags for that). It looks like
        it would really embed that code in the libraries, but I'm not sure yet if it could 
        cause name conflicts when the original is also linked.

-   Still difficulties with zlib. As soon as we use an external lz4 and zstd, it doesn't seem
    to pick zlib up anymore. It could be because it only comes in as a dependency for building
    zstd?


### Version 2.23.1 for 26.03

-   Developed because it turned out that ADIOS2 doesn't like the 3.x versions of Blosc2.

-   This version does not download external sources but already includes them. Yet we chose to
    use external versions.

-   Same issue with zlib as we had with version 3.2.3.

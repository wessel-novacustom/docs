# Standard Release Process

Following procedure is generic description of release process of firmware for
supported hardware platforms. Precise steps and any difference from standard
process are described in platform specific documentation.

Description here is, intentionally, open-source firmware framework agnostic and
should be maintained in that way.

## Process steps

1. Checkout new branch `<platform>_rel_vX.Y.Z` from recent commit on `dasharo`
   branch - to understand versioning scheme please read [Versioning](versioning.md)
   section
2. Merge current platform development branches to `<platform>_rel_vX.Y.Z`
3. (Optional) Create a release candidate by tagging `<platform>_vX.Y.Z-rcN`
4. Run platform regression test suite
5. Fix all required issues and repeat from point 3 until fixed - this doesn't
   mean all tests pass, this mean that approved set passed
6. If results are accepted merge it to `dasharo` branch
7. Add tag, which should trigger CI and publish binaries. Tag should be
   annotated and signed. For example:

    ```bash
    git tag -a -s -m "<platform>_vX.Y.Z" <platform>_vX.Y.Z
    ```

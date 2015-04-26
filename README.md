CAF-victara
===========

Getting Started
---------------

See [The AOSP Build Guide](https://source.android.com/source/building.html) for instructions on getting started.

Using this tree, you will also need to install liblz4:

    sudo apt-get install liblz4-tool

Getting the Source
------------------

Follow the instructions for [installing repo](https://source.android.com/source/downloading.html#installing-repo).

To initialize a local repository using the CAF-victara trees:

    mkdir caf-victara && cd caf-victara
    repo init -u git://github.com/CAF-victara/platform_manifest.git -b lollipop-5.1.0-unofficial-victara

Then to download the sources:

    repo sync -c -j#

where # is the number of threads you wish to use.

This process may take a long time, so be patient. You may have to run the sync multiple times before successfully retrieving all sources.

Building
--------

Once you've downloaded all of the sources (it's a lot, be patient), you can start the build process.

    . build/envsetup.sh
    lunch aosp_victara-userdebug
    make otapackage -j#

where, once again, # is the number of threads you wish to use.

This process also takes quite a while, but the final result will be a flashable zip found in out/target/product/victara/

How many threads should I use?
------------------------------

That is largely dependent on your personal setup. The general rule of thumb is to use the number of logical cores of your processor.

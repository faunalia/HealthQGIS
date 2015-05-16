How to create a Windows package of QGIS
---------------------------------------

1. clone the QGIS repo on your machine `git clone https://github.com/qgis/QGIS.git`

2. go in the folder `ms-windows/osgeo4w` inside the repo

3. ``aptitude install nsis``

4. you can now easily create a package using the ``creatensis.pl`` script. Just type in a terminal ``perl creatensis.pl``


.. warning:: this procedure, especially the first time, will take a while. The script will download all the package from the osgeo server and then it will package them together

.. note:: type ``perl creatensis --help`` to see all the options available

.. note:: by default, ``creatensis`` creates the lastest stable release of QGIS, so if you want to build a master versione you have to specify it through the option ``-version=qgis-dev``

5. you will find the final package (for 64bit if you didn't specify the architecure) in the ``ms-windows`` folder of the repo. You can simply copy this file and install QGIS on a Windows machine

6. `creatensis` is a very powerful tool that allows to create a customized QGIS. This means that you can include additional plugins, configuration files, etc..

   #.  create the `addons` directory in ``ms-windows/osgeo4w``
   #.  create the `bin` directory in the `addons` one. This directory should contain the ``qgis.bat.tmpl`` file: this file will be converted in the ``qgis.bat`` file, so the file that launch QGIS on windows
   #.  if you want to add some configuration, I strongly suggest to use the ``--configpath`` option when launching QGIS. This option will create ordered folders where **all** your customizations will be put together (plugins included). So create the ``qgisconfig`` folder (the name here is not important, but you have to put the name of this directory in the ``qgis.bat.tmpl`` file, so take care to remember it) and type in a terminal ``qgis --configpath ~/QGIS/ms-windows-osgeo4w/addons/qgisconfig``. This way all your customizations will be included in the repository. Otherwise you have to copy the content of the ``--configpath`` folder in ``qgisconfig``
   #.  you can also include some data and a project file in tha package. But there are some issues with large files, so maybe this insn't a great idea

7. now you have to edit the ``qgis.bat.tmpl`` file in order to include the customization in the package. This is the final version of the ``qgis.bat.tmpl`` file::

    `call "%~dp0\o4w_env.bat"
    @echo off
    call "%OSGEO4W_ROOT%"\apps\grass\grass-6.4.3\etc\env.bat
    @echo off
    path %OSGEO4W_ROOT%\apps\qgis\bin;%OSGEO4W_ROOT%\apps\grass\grass-6.4.3\lib;%PATH%
    set QGIS_PREFIX_PATH=%OSGEO4W_ROOT:\=/%/apps/qgis
    set GDAL_FILENAME_IS_UTF8=YES
    rem Set VSI cache to be used as buffer, see #6448
    set VSI_CACHE=TRUE
    set VSI_CACHE_SIZE=1000000
    mkdir "%USERPROFILE%\.qgis-custom" 2>nul 
    if not errorlevel 1 (xcopy "%OSGEO4W_ROOT%\qgisconfig" "%USERPROFILE%\.qgis-custom" /s /v /e)
    start "QGIS" /B "%OSGEO4W_ROOT%"\bin\qgis-bin.exe %* --configpath %USERPROFILE%\.qgis-custom`

Enjoy!






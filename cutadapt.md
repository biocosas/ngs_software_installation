Build cutadapt
================

The latest version (__1.5__ when I wrote this) is available at: 
<https://github.com/marcelm/cutadapt>


It comes with a compiled `bin/cutadapt` which may be used directly. 
If it does not work you will need to _build_ it.

Dependencies
------------

    sudo apt-get install python-dev
    sudo apt-get install cython 
    (sudo) apt-get install cython-dbg cython-doc   # I am not sure this is needed 

----

[Cython](http://cython.org/) may also be installed in __your home__ directory (in case you do not have root access):

- Download Cython form <http://cython.org/#download>
- Decompress 
- Change to the uncompressed folder and type: `python setup.py install --user`

Still `python-dev` needs to be installed (I do not know if there is a local way to install this or if it has to be installed via apt)

Sometimes the latest version of `cython` may be needed. 
Download form <https://github.com/cython/cython> and follow the INSTALL instructions:
    
    unzip 
    cd cython-0.21.2
    sudo python setup.py install



Build
----------------

    tar -xzvf cutadapt-1.5.tar.gz 
    cd cutadapt-1.5/
    
    python setup.py build
    python setup.py build_ext -i               # -i is just for verbose output
    
<!--     
    cp bin/_preamble.py build/scripts-2.7/     # this is needed for a custom installation


Then the script 

    build/scripts-2.7/cutadapt
-->

Then the script 

    bin/cutadapt

seems to work fine. 

You can directly call it or include it in your path.



Note
--------------------

Do not remove the `bin/cutadapt` file in the original bin directory. It seems to be used during the `python setup.py`


# Setup #

Leaf is very easy to compile and setup. Here are some step by step instructions

# Instructions #

#1. If your running a Debian based operating system such as Ubuntu you will need to apt-get some tools:

**apt-get install gcc libc6-dev make libtool autoconf git-core**

#2. Now you need to get udis86 from its git repository.

**git clone git://udis86.git.sourceforge.net/gitroot/udis86/udis86**

#3. Download and unpack the Leaf code.

**tar xvzf leaf-XYZ.tar.gz**

#4. cd into the Leaf directory

**cd leaf-XYZ/**

#5. Run the installation script. You will need permissions to create the /opt/leaf directory.

**./INSTALL.sh**

#6. Leaf should be installed at this point. You can run it to make sure.

**leaf -h**

#7. You can compile and install plugins easily. Their default install directory is _/opt/leaf/plugins_

**cd shell\_out/**

**make**

**make install**

#8. Now if you want to load only the shell\_out plugin at runtime do the following.

**leaf -f /bin/ls -u shell\_out.leaf**

Otherwise all plugins found in _/opt/leaf/plugins_ will be loaded

# Note(s) #

Leaf is built using the latest version of udis86 from its git repository. Its possible that the version of udis86 you checked out is different from the version I had when I wrote Leaf. This **may** cause some issues when compiling Leaf or a plugin like LeafRub. If you get errors like:

```
LeafRub.c: In function ‘LEAF_init’:
LeafRub.c:458: error: ‘INVEPT_INST’ undeclared (first use in this function)
LeafRub.c:458: error: (Each undeclared identifier is reported only once
```

Then do the following:

**cd leaf/source/include**

**ruby udis\_wrap\_create.rb**

Now re-run the leaf INSTALL.sh script. Everything should be fixed. The udis\_wrap\_create.rb **REQUIRES** your udis86 git checkout be located at /usr/src/udis86. This is because udis\_wrap\_create.rb reads a bunch of values from udis86 headers and generates custom enum's used by Leaf.
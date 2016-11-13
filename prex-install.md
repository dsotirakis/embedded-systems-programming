#Prex Installation

The following tutorials are based on 32-bit Linux Debian Architecture that can be found [here](http://cdimage.debian.org/debian-cd/8.6.0/i386/iso-cd/debian-8.6.0-i386-netinst.iso).

1. Open a terminal and write: <code> su </code>

2. Enter the root password and type: <code> apt install sudo </code>

3. Enter: <code> visudo </code>

4. Find:

<code>
//User priviledge specification
root	ALL=(ALL:ALL) ALL
</code>

...and add below the following:

<code> username	ALL=(ALL:ALL) ALL </code>

where username is your system username. Save the script by hitting Ctrl+O and Ctrl+X.

Then enter exit.

5. Because prex is using an older version of gcc, it is required that we download the necessary files.

-cpp-4.1_4.1.1-21_i386.deb <br />
-gcc-4.1_4.1.1-21_i386.deb<br />
-gcc-4.1-base_4.1.1-21_i386.deb<br />
-libgcc1_4.1.1-21_i386.deb<br />
-libssp0_4.1.1-21_i386.deb<br />

They can be found [here](http://archive.debian.org/debian/pool/main/g/gcc-4.1/).

6. Go to the folder that they downloaded, and execute the following by strict order:


<code>sudo dpkg -i gcc-4.1-base_4.1.1-21_i386.deb</code><br />
<code>sudo dpkg -i cpp-4.1_4.1.1-21_i386.deb</code><br />
<code>sudo dpkg -i libgcc1_4.1.1-21_i386.deb</code><br />
<code>sudo dpkg -i libssp0_4.1.1-21_i386.deb</code><br />
<code>sudo apt install binutils</code><br />
<code>sudo apt -f install</code><br />
<code>sudo dpkg -i gcc-4.1_4.1.1-21_i386.deb
</code><br />

<b> DON'T FORGET THAT ON COMPILATION, THE COMMAND IS gcc-4.1 AND NOT gcc. </b>

7. Now download the files from this -embedded-systems-programming- repository. 

8. In the console, move to the prex-0.9.0 folder. Run:

<code>sudo apt install make </code><br />
./configure --cc=gcc-4.1 --target=x86


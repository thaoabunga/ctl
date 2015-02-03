===== README ======
Thanks for downloading The Computational Topology library!

This C++11 library provides a set of generic tools for:
	1) Generating point sets (coming soon)
	2) Building Neighborhood Graphs (coming soon)
	3) Building Cellular Complexes (coming soon)
	4) Computing [persistent] homology over finite fields
	5) Parallel algorithm(s) for (4)

=== LICENSE ===
CTL is BSD See LICENSE for more info. 

=== DEPENDENCIES ==
CTL has a number of dependencies. We have listed them below.

We have made an effort to make getting an using these dependencies simple.

In particular, we strongly recommend installing them on your system either
as root or with the help of your system adminstrator via your operating systems
package manager e.g. apt on debian based systems, yum on RHEL systems, or 
brew/port/fink on OSX.


If you do not tell us specifically where these dependencies are, we will try to
find them for you via the CMake `find_package` system. 

If this fails, but you have a local/system wide install of the library, 
simply update the corresponding entries in:
	build_dependencies.txt

If you do not have the software installed anywhere, then for some of our 
dependencies we provide make targets to download, and install them on your 
system.

For example:
	`make gtest`

Will download and install gtest into the dependencies/ directory.

For your convienence `build_dependencies.txt` already lists the directories
where this software should be installed to. So just uncomment!

If you encounter any issues, make sure to file it:
  https://github.com/appliedtopology/ctl/issues

This list of the dependencies is below and we have annoted 
which packages we can auto-help you install locally.

C++11 compiler (clang or gcc)
GTest (make gtest)
MPI 
Boost with MPI (make boost)
Intel's TBB 
METIS (make metis) (used for graph partitioning)
ANN (make ann)
Doxygen (Optional)

=== BUILDING ====
Step 1) Make sure you have all the dependencies and you know the paths to the 
						     include/link directories
Step 2) Fill out the relevant bits of `build_dependencies.txt`

Step 3) Create makefiles
	cmake .
Step 4) Compile: (the -j option makes in parallel)
	make -j 

=== For OS/X Users: ===  
If you plan on using the default compiler (clang)
then when installing boost ensure that you use:
	brew install boost ---build-from-source --with-c++11 --with-mpi --with-program_options --with-clang --without-single
and after `cmake .` ensure that the compiler chosen is clang via `ccmake .` /usr/bin/c++ 
is a good choice.

Since libstdc++ (GNU C++ STL) and libc++ (Clang C++ STL) are not ABI compatible
one needs to take care to use the correct compilers for libraries linked against.
if boost is compiled with gcc, you cannot use clang to compile CTL and vice versa.


=== INSTALL === 
-- We don't recommend doing this unless you are really desperate. --
 --- And even then watch out for zombies. --- 

Fedora/CentOS/RHEL:
yum install ctl (coming soon)

Ubuntu:
apt-get install ctl (coming soon)

OS/X
brew tap appliedtopology/software
brew install ctl

=== INSTALL (from source) ===
make install

There are no shared libraries!

==== USING (coming soon) ====
See /usr/share/doc/examples for a number of examples of using the library. 
See tutorial/ for a tutorial 

==== SUBMITTING PATCHES ====
Please Do! Accepting Pull Requests via github.

In the future we hope to add support for:
	0) [Persistent] Co-homology
	1) Zig Zag Persistence
	2) Multidimensional Persistence
	3) Multidimensional Zig-Zag Persistence
	4) Tidy Sets
	5) Persistent Landscapes
	6) OpenGL Visualizations
	7) Bindings to other languages such as Python, MATLAB, and R
# opencv_with_cuda
<b>
A simple tutorial on how to install opencv with cuda (ubuntu 14.04):
</b>


1. First of all, download cuda from the following url: https://developer.nvidia.com/cuda-downloads.
After that, install cuda on your machine:
<pre><code>~/Downloads$ sudo dpkg -i cuda-repo-ubuntu1404-7-5-local_7.5-18_amd64.deb
~/Downloads$ sudo apt-get update
~/Downloads$ sudo apt-get install cuda</code></pre>


2. After you've installed cuda, let's install opencv with all the required packages:
<pre><code>sudo apt-get update
~$ sudo apt-get install build-essential
~$ sudo apt-get install cmake git libgtk2.0-dev pkg-config libavcodec-dev libavformat-dev libswscale-dev
~$ sudo apt-get install python-dev python-numpy libtbb2 libtbb-dev libjpeg-dev libpng-dev libtiff-dev libjasper-dev libdc1394-22-dev</code></pre>


3. Go ahead and get the latest cutting edge opencv from the git repository:
<pre><code>~$ mkdir my_opencv_dir
~$ cd my_opencv_dir
~/my_opencv_dir$ git clone https://github.com/Itseez/opencv.git</code></pre>


4. Install opencv (with cuda and opengl support) to /usr/local:

  Generate the makefiles:
<pre><code>~/my_opencv_dir$ cd opencv
~/my_opencv_dir/opencv$ mkdir release
~/my_opencv_dir/opencv$ cd release
~/my_opencv_dir/opencv/release$ cmake -D CMAKE_BUILD_TYPE=RELEASE -D WITH_CUDA=ON -D WITH_TBB=ON -D BUILD_NEW_PYTHON_SUPPORT=ON -D WITH_V4L=ON -D INSTALL_C_EXAMPLES=ON -D INSTALL_PYTHON_EXAMPLES=ON -D BUILD_EXAMPLES=ON -D WITH_QT=ON -D WITH_OPENGL=ON -D WITH_CUBLAS=1 -D CMAKE_INSTALL_PREFIX=/usr/local ..  </code></pre>
*Scroll up in the terminal and make sure that cuda is enabled (Use Cuda: YES).

  Install opencv:
<pre><code>~/my_opencv_dir/opencv/release$ make
~/my_opencv_dir/opencv/release$ sudo make install</code></pre>


That's it, you're good to go :)
 

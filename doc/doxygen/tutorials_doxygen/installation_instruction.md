
Installation Instructions {#installation_instruction} 
=========================

 [TOC]
 
The compilation and installation of OD is fairly simple. You first have to install its dependencies before compiling. Folllowing are the dependencies with their specific settings:


Dependencies {#tag1}
============


##OpenCV 3.0## {#tag2}

OpenCV 3.0 is to be compiled with the modules xfeatures2d (for features like SIFT) and CUDA.
    
- **Source:** http://opencv.org/downloads.html or https://github.com/Itseez/opencv              
    
- **Required settings:**

    - *OpenCV contrib* - for xfeatures2d module handing SIFT/SURF features
        
        Detailed instructions with source are provided here: https://github.com/itseez/opencv_contrib . You need to download this seperate repository before compiling OpenCV.
                
        *CMAKE options*: OPENCV_EXTRA_MODULES_PATH=<path_to_opencv_contrib>/modules
                                              
    - *OpenCV CUDA module* - for GPU enabled feature detectors and matcher.
             
        *CMAKE options*: WITH_CUDA=ON       

 
##VTK 6.0 or above {#tag3}
    
Download and compile latest VTK with its default settings.
    
   
##PCL 1.6 or above {#tag4}   
    
- **Source:** https://github.com/PointCloudLibrary/pcl or https://github.com/PointCloudLibrary/pcl/releases

- **Required settings:**

  * *3d_rec_framework* - for ESF, ESF etc recognition pipeline.
  
      *Additional CMAKE options:* BUILD_apps=ON, BUILD_apps_3d_rec_framework=ON
    
##Eigen {#tag5}
Get the latest version of Eigen (source) using your package manager.


Installing Open Detection {#tag6}
====

With the above dependencies installed, OD should compile without any problem. Download the source from https://github.com/krips89/opendetection and compile it with default cmake options. The code while platform independent, is only tested and run in Linux machine. Instructions for the usage for linux are provided below: 

##Instructions: {#tag7}
Compile out of source using cmake+your favorite compiler. For example:

Download the code: 
@code{.bash}
cd <path_to_desired_download_location>
git clone https://github.com/krips89/opendetection.git
@endcode

configure with CMake and compile 
@code{.bash}
cd <path_to_source>
mkdir build; cd build
cmake ..
make -j8
make install
@endcode



  
# Free Version
A featured-limited version of the http://SDR4.space/ embedded software, originally designed for embedded GPU systems.


## Releases

 * __x86__  
The x86_64 version available as realease runs under Linux systems and __doest not support GPU__.  

 * __Jetson Nano__  
The NanoSDR version has been tested on Jetson Nanao DevKit and __supports GPU acceleration__  
It has been tested on our custom image available for download here : https://github.com/SDR-Technologies/NanoSDR
 

# Documentation

The doc is available here : http://sdr4.space/doc/ (english only).  
Basic examples based on the documentation are available here : https://github.com/SDR4space/Examples/

## Tutorial

Thanks to Aaron from DragonOS team for this Youtube tutorial on sdr4space.lite basics :  
https://www.youtube.com/watch?v=BxOK9Gzz7hg

# Installation

### Debian package (.deb)

Install SoapySDR 0.8 (and device sub-modules) [from sources](https://github.com/pothosware/SoapySDR/releases/tag/soapy-sdr-0.8.0)
Download the sdr4space_lite.deb file and run dpkg installer:   

```
wget https://github.com/SDR4space/FreeVersion/raw/main/sdr4space_lite.deb
sudo dpkg -i sdr4space_lite.deb
```

The binary sdr4space.light executable file is then installed in */opt/vmbase* . 

```
  ./sdr4space.light --help
---------------------------------------------------------------------------------
 SDR4.Space Version b1d5b5e3571afd9f5cee649b609507d0ccf0c18e - Build : 20210605
      (c) SDR-Technologies SAS - http://sdr4.space/
---------------------------------------------------------------------------------
Creating Radio Device factory
 Disk free space : 21.0 % 
JavaScript SDR/Sat/DSP and more
Usage:
  sdrvm [OPTION...]

  -t, --timing       Enable timing for each running task
  -h, --help         Print usage
  -f, --file arg     Script file name
  -d, --workdir arg  working directory, default is program location 
  -v, --verbose      Verbose mode (default: true)
```
### .AppImage file

Download latest AppImage file from our [releases](https://github.com/SDR4space/FreeVersion/releases)  
Make it executable ( `chmod +x SDR4space-lite.AppImage`) and run it.  

* Notes:  
All needed dependencies are in the AppImage file, including SoapySDR v0.8  
First version v0.1 supports RTLSDR and plutoSDR devices only.

#### Test 

Notice the '0% Disk free space' : we are in a read-only environment.  
 
```
/home/user/Downloads/sdr4space_lite/SDR4space-lite.AppImage --help

---------------------------------------------------------------------------------
 SDR4.Space Version b1d5b5e3571afd9f5cee649b609507d0ccf0c18e - Build : 20210716
      (c) SDR-Technologies SAS - http://sdr4.space/
---------------------------------------------------------------------------------
Creating Radio Device factory
 Disk free space : 0.0 % 
JavaScript SDR/Sat/DSP and more
Usage:
  sdrvm [OPTION...]

  -t, --timing       Enable timing for each running task
  -h, --help         Print usage
  -f, --file arg     Script file name
  -d, --workdir arg  working directory, default is program location 
  -v, --verbose      Verbose mode (default: true)
```


# running / testing

Create a test file, for example hello.js :  
```
  print('hello world!');
```
  
 Then run it :  
```
  ./sdr4space.light -f ./test.js 
---------------------------------------------------------------------------------
 SDR4.Space Version b1d5b5e3571afd9f5cee649b609507d0ccf0c18e - Build : 20210605
      (c) SDR-Technologies SAS - http://sdr4.space/
---------------------------------------------------------------------------------
Creating Radio Device factory
 Disk free space : 21.0 % 
 VM starting...

 Loading : [./test.js]

(boot:0)> hello world!

No running task, ending.

```

The Virtual Machine stops when no task is running.

# Dependencies 

The dpkg installer should be able to install needed dependencies by itself.

In case of trouble or for manual installation, the following packages are required :
* SoapySDR, __version 0.8__
* fftw3-3
* liquid-sdr (libliquid1d)
* libsndfile1
* libliquid1d
* mosquitto
* mosquitto-clients


Note for Liquid-SDR :
* This library can be downloaded and installed from source following instructions from https://github.com/jgaeddert/liquid-dsp
* For Ubuntu 18.04 or 20.04, a package is available here : https://ubuntu.pkgs.org/18.04/ubuntu-universe-amd64/libliquid1d_1.3.1-1_amd64.deb.html



# Support - Bug reports

While full support is provided to our commercial customers, free-version users should use the GitHub issue tracking.


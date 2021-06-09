# Free Version
A featured-limited version of the http://SDR4.space/ embedded software, originally designed for embedded GPU systems.

This version runs only on x86-64 Linux systems and __doest not support GPU__.

# Documentation

The doc is available here : http://sdr4.space/doc/ (english only).  
Basic examples based on the documentation are available here : https://github.com/SDR4space/Examples/

# Installation

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


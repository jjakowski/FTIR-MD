
The co2 example contains two folders  "run-1"  and run-x100".
   First 100 MD simulations with DFTB+ for a gas phase co2 was run on expanse (SDSC).  
   Each were stored in individual folder run-1, run-2,... run-100.
    For each  DFTB run  the FTIR was calculated and stored in a FTIR subfolder
   Next all  FTIR run spectra were accumulated to get a statiscially meaning spectrum for CO2.
    The need  for  using statistics instead fo a single MD run is following:  a single MD run  will put a "random" 
    amount of energy into each vibrational degree of freedom,  so  the intensities from  a single run are not really 
    representative   of actual run, especially for NVE ensemble. 
    For NVT ensemble one may expect that thermostat corrects intensities,  but  it may  bias frequencies since the thermostat 
     may add some extra push or pull to velocities.


  run-1               #  Example folder  from a single DFTB+ run of MD with NVE. 
                         This folder stores  DFTB files from a single run as well as all scripts to generate  IR/power spectra 
  run-x100            #   Example folder will spectra from run-1,run-2, etc.  summed up and final  FTIR/power spectra are generated
                           The results are compaded with experimental data  as shown in  "co2-benchmark-100runs.pdf" file
                          Notice that MD  based FTIR reproduce well anharmonicy (see the "wings" on both sides of bending peak  ~550cm-1)






============================
There three version of workflow script   for generatic IR/powers  spectra:

1)  readme-vels        :  uses in-house routines for auto-correlation  for fourier transform
                          "octave-autocorr.inp"    and jfft() in "octave-fft1d-jj.m*"
                          This should work everywhere.

                          Timing  (slow):  16min:34 sec  on bigroo
                   
2) readme-vels-fast    :  uses "conv()"  routine to  get auto-correlation 
                          This version uses  "octave-autocorr2.inp". 
                          Make sure to use  "fft()" rather than  "jfft()" in "octave-fft1d-jj.m*"
 
                          Timing (fast):  1 min:28 sec on bigroo

3) readme-vels-fastest :  uses "xcorr()" routine from  octave's external packages "signal"
                          This version requires installing octave' external packages "signal" and "control"
                          Make sure to use  "fft()" rather than  "jfft()" in "octave-fft1d-jj.m*"
                          This version uses  "octave-autocorr3.inp". 
                        
                          Timing (very fast)  :  0 min 18 sec


Summary of timing  on bigroo:
------------------------------------
FTIR-MD/Examples/co2/run-1-test/FTIR$ date ; bash readme-vels   ; date 
Wed Jun  8 11:46:20 EDT 2022
Wed Jun  8 12:02:54 EDT 2022
              16:34  min
-------------------------
./FTIR-MD/Examples/co2/run-1-test/FTIR/tmp$ date ; bash readme-vels-fast ; date 
Wed Jun  8 11:43:48 EDT 2022
Wed Jun  8 11:45:15 EDT 2022
               1:28  min
-------------------------
./FTIR-MD/Examples/co2/run-1-test/FTIR/tmp2$ date ; bash readme-vels-fastest  ; date 
Wed Jun  8 11:45:44 EDT 2022
Wed Jun  8 11:46:02 EDT 2022
               0:18 sec


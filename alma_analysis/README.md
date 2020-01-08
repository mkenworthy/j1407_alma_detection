# ALMA J1407 analysis

ALMA data reduction and analysis by Pamela Klaassen pamela.klaassen@stfc.ac.uk

## SOURCE SIZE

This comes from `imfit`, and can be reproduced using the `imfit` command.

## SOURCE FLUX

`imfit` gives an estimate of the flux (integrated and peak) for the target, but don't trust the noise estimates on it.  For instance, the fit for the peak intensity is 98+/-12 muJy/beam.  This 98 must be extrapolated to infinite resolution observations, because the peak in the box is 89 muJy/beam (as quantified by imstat, see below).

To get a better estimate of the signal and noise levels, I used imstat (commands listed at bottom of this comment block), with boxes limiting the regions of interest (with pixel edges defined below in 'sigal box' and 'noise box'.  The noise box is *fairly* small (but still 61x larger than the box used to determine the signal).  The reason it's so 'small' is to keep it close to the centre of the primary beam. I don't want the drop off in sensitivity to interfere with the rms noise determination.

imstat peak:   89.42 muJy/beam
imstat noise: 19.2 muJy/beam
rounded SNR:  4.7

signal box = '1448,1473,1480,1501'
noise box = '1495,1278,1623,1705'
(formatting: 'x1,y1,x2,y2' - the noise box should be a narrow veritcal box)

## Statistical analysis

### imfit command for finding location of target

    imfit(imagename="uid___A001_X87c_X409._1SWASP_J140747.93-394542.6__sci.spw17_19_21_23.cont.I.pbcor.fits",box="1448,1473,1480,1501",region="",chans="",stokes="",mask="",includepix=[],excludepix=[],residual="",model="",estimates="",logfile="",append=True,newestimates="",complist="",overwrite=False,dooff=False,offset=0.0,fixoffset=False,stretch=False,rms=-1,noisefwhm="",summary="")

### imstat for target peak (imstat 'max' value)

    imstat(imagename="uid___A001_X87c_X409._1SWASP_J140747.93-394542.6__sci.spw17_19_21_23.cont.I.pbcor.fits",axes=-1,region="",box="1448,1480,1473,1501",chans="",stokes="",listit=True,verbose=True,mask="",stretch=False,logfile="",append=True,algorithm="classic",fence=-1,center="mean",lside=True,zscore=-1,maxiter=-1,clmethod="auto",niter=3)

### imstat for region rms (imstat 'rms' value)

    imstat(imagename="uid___A001_X87c_X409._1SWASP_J140747.93-394542.6__sci.spw17_19_21_23.cont.I.pbcor.fits",axes=-1,region="",box="1495,1278,1623,1705",chans="",stokes="",listit=True,verbose=True,mask="",stretch=False,logfile="",append=True,algorithm="classic",fence=-1,center="mean",lside=True,zscore=-1,maxiter=-1,clmethod="auto",niter=3)

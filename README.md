# SpikeInterface Hands on for spike sorting

Material for the hands on session of the CNN Master

## Schedule


# Installation

See [installation page](https://github.com/samuelgarcia/school_spike_sorting_neuralnet_bordeaux_2025/blob/main/installation.md)


# Overview of available datasets

If you have to pick only one file to download, because of disk usage, it has to be the first one, **M25_D23_2024-11-11_13-11-10_OF1**, since it will be the most used during the Tutorials. The download link is https://filesender.renater.fr/?s=download&token=f94a08b3-e779-4911-90bf-a312c3c34a01
**Please do think about unzipping the data prior to the school!**

## In vivo

### M25_D23_2024-11-11_13-11-10_OF1

Neuropixels 2.0 dataset (384 channels) acquired with the Open Ephys GUI in binary format.
You can use the `spikeinterface.extractor.read_openephys()` function to read the data.

### 1544_2023-04-21_09-55-34_of

Recording with 16 channels organized in 4 tetrodes acquired with the Open Ephys GUI in "openephys" format.
You can use the `spikeinterface.extractor.read_openephys()` function to read the data.


## In vitro

### mouse_CTX_14D.brw

Primary mouse cortex for E18 embryos. Plated 80K on CorePlate 1W38/60 3Brain, recorded after 14 days in culture 
with 3Brain BioCAM system. 
You can use the `spikeinterface.extractor.read_biocam()` function to read the data. 


### human_ngn2_100K_c_55D.brw

Human glutamatergic neurons induced via ngn2 method. Plated 100k on CorePlate 1W38/60 3Brain, recorded after 55 days in 
culture with 3Brain BioCAM system. 
You can use the `spikeinterface.extractor.read_biocam()` function to read the data. 

> [!IMPORTANT]  
> The 3Brain BioCAM system saves the data in unsigned integers. You should convert it to signed integers for a smooth
> processing. See documentation [here](https://spikeinterface.readthedocs.io/en/latest/how_to/unsigned_to_signed.html). Note that the `bit_depth` for this system is 12!


Please download these datasets on your laptop from this link:

https://filesender.renater.fr/?s=download&token=f94a08b3-e779-4911-90bf-a312c3c34a01

[![Abcdspec-compliant](https://img.shields.io/badge/ABCD_Spec-v1.1-green.svg)](https://github.com/brain-life/abcd-spec)
[![Run on Brainlife.io](https://img.shields.io/badge/Brainlife-bl.app.1-blue.svg)](https://doi.org/10.25663/bl.app.1)

# app-converttck2trk

This service will convert .tck files to .trk files using nipype. 

### Authors
- Lindsey Kitchell (kitchell@indiana.edu)

### Contributors
- Soichi Hayashi (hayashis@iu.edu)

### Funding 
[![NSF-BCS-1734853](https://img.shields.io/badge/NSF_BCS-1734853-blue.svg)](https://nsf.gov/awardsearch/showAward?AWD_ID=1734853)

### References 
[1. MRTrix2TrackVis](https://nipype.readthedocs.io/en/latest/interfaces/generated/interfaces.mrtrix/convert.html)

## Running the App 

### On Brainlife.io

You can submit this App online at [https://doi.org/10.25663/bl.app.22](https://doi.org/10.25663/bl.app.22) via the "Execute" tab.

### Running Locally (on your machine)

1. git clone this repo.

2. Inside the cloned directory, create `config.json` with something like the following content with paths to your input files.

```json
{
        "track": "./input/track/track.tck",
	"dwi": "./input/dtiinit/dwi_aligned_trilin_noMEC.nii.gz"
}
```

If you have singularity installed on your local machine:

3. Launch the App by executing `main`

```bash
./main
```

Otherwise:

3. Ensure you have the proper dependencies installed for python and execute main.py directly. 

### Sample Datasets

If you don't have your own input file, you can download sample datasets from Brainlife.io, or you can use [Brainlife CLI](https://github.com/brain-life/cli).

```
npm install -g brainlife
bl login
mkdir input
bl dataset download 5a0e604116e499548135de87 && mv 5a0e604116e499548135de87 input/track
bl dataset download 5a0dcb1216e499548135dd27 && mv 5a0dcb1216e499548135dd27 input/dtiinit
```

## Output

The main output of this App is a file called `track.trk`. 


### Dependencies

This App only requires [singularity](https://www.sylabs.io/singularity/) to run. If you don't have singularity, you will need to install following dependencies.  

  - NIPYPE: https://nipype.readthedocs.io/en/latest/
  - H5PY: https://www.h5py.org/


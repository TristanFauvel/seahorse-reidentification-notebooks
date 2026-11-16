# Open-set multi-view seahorse re-identification

The notebooks of *Automated open-set multi-view seahorse re-identification from underwater photograph
sequences*.  


## Installing

```bash
pip install -r requirements.txt
pip install "lightglue @ git+https://github.com/cvg/LightGlue.git"   # not on PyPI
```

Python 3.11 or newer. SAM 3 needs `transformers>=5.0`.

SAM 3 is gated on Hugging Face, and the notebooks never download it. Accept its licence, log in
(`hf auth login`), and download it once into the `models/` folder of `cache_dir`:
`hf download facebook/sam3 --local-dir <cache_dir>/models/sam3` (3.3 GB).

## The data
`data_root` must contain:

```
seahorse_photo_database.xlsx   sheets "Photos" and "Individual_Summary"
segmented/                     full-resolution masked crops (*.png), from notebook 1 
segmented_compressed/          the same crops, longest edge 2048 (*.jpg)
```

Photographs are named `SH<individual>_<observation>_<photo>`.   

## Outputs

The notebooks print every table of the paper as booktabs LaTeX, and write the figures to
`<output_dir>/figures/`. 

## Citation

If you use this code, please cite the paper: 
@online{fauvel_openset_2026,
  title = {Automated Open-Set Multi-View Seahorse Re-Identification from Underwater Photograph Sequences},
  author = {Fauvel, Tristan and Louisy, Sylvie and Louisy, Patrick and Fauvel, Thomas},
  date = {2026-10-29},
  eprint = {2610.39857},
  eprinttype = {arXiv},
  eprintclass = {cs.CV},
  doi = {10.48550/arXiv.2610.39857},
  url = {http://arxiv.org/abs/2610.39857},
  urldate = {2026-11-16},
  langid = {english},
  pubstate = {prepublished}
}

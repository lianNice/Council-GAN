# GAN-Council
implementation of our paper Breaking the Cycle - Colleagues are all you need 
### Paper
[Ori Nizan](https://onr.github.io/) , [Ayellet Tal](http://webee.technion.ac.il/~ayellet/),
**[Breaking the Cycle - Colleagues are all you need](https://arxiv.org/abs/1911.10538 "Breaking the cycle -- Colleagues are all you need")**

![gan_council_overview](/images/gan_council_overview.png)

## Usage

### Downloading the dataset
download the selfie to anime dataset:

    bash ./scripts/download.sh selfie2anime

download the celeba glasses removal dataset:

    bash ./scripts/download.sh celeba_glasses_removal
    
download the celeba male to female:

    bash ./scripts/download.sh celeba_male2female
    
### Training:
#### selfi2anime: 
    python train.py --config configs/anime2face_council_folder.yaml --output_path ./outputs/council_anime2face_256_256 --resume 

#### glasses removel:
    python train.py --config configs/galsses_council_folder.yaml --output_path ./outputs/council_glasses_128_128 --resume 
    
#### male to female:
    python train.py --config configs/male2female.yaml --output_path ./outputs/male2famle_256_256 --resume 


### Testing:
for converting all the images in input_folder using all the members in the council:

    python test_on_folder.py --config configs/anime2face_council_folder.yaml --output_folder ./outputs/council_anime2face_256_256 --checkpoint ./outputs/council_anime2face_256_256/anime2face_council_folder/checkpoints/01000000 --input_folder ./datasets/selfie2anime/testB --b2a
    
or to spsified memeber with

    python test_on_folder.py --config configs/anime2face_council_folder.yaml --output_folder ./outputs/council_anime2face_256_256 --checkpoint ./outputs/council_anime2face_256_256/anime2face_council_folder/checkpoints/b2a_gen_3_01000000.pt --input_folder ./datasets/selfie2anime/testB --b2a
#### Citation

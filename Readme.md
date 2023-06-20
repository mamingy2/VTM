Please apply the patches from the commit 813be3856357bf0cd974670495d51a73ecf72e56.   
The VTM version is based on Tag 19.2

The 0001-patch is used to encode and rewrite during the when encoding.  
The 0002/3-patch added the SkipAPP and SkipLib (mainly based on the DecoderLib, partly based on EncoderLib).  
The 0004-patch is used to read, modify and rewrite the bitstream and syntax.

CmdLines:  
sudo ./EncoderAppStaticd -c ../cfg/encoder_lowdelay_P_vtm.cfg -c ../cfg/partitioning/512.cfg  -c ../cfg/multi-layer/two_layers.cfg -l0 -c ../cfg/per-sequence/Cactus_256.cfg -l1 -c ../cfg/per-sequence/Cactus_512.cfg --MultiLayerEnabledFlag=1 --BitstreamFile=SVC_two_layer_skip_idx_tile.bin  
sudo ./SkipAppStatic -b SVC_two_layer.bin  

### TODO:
1. In Encoder, some of the rewrite stream is not right when decoding (but VQAnalyzer can show it).
2. Some of the Skip rewrite results are not right and cannot be decoded.

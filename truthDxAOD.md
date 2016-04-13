# DxAOD Truth


```bash
pathena \
  --cmtConfig=x86_64-slc6-gcc48-opt \
  --useNewTRF \
  --trf \
    "Reco_tf.py \
     --inputEVNTFile %IN \
     --outputDAODFile test.pool.root \
     --ignoreErrors=True \
     --reductionConf TRUTH1 \
     --maxEvents -1" \
  --extOutFile DAOD_TRUTH1.test.pool.root \
  --nFilesPerJob=1 \
  --individualOutDS \
  --inDS user.<grid_user_name>.mc15_13TeV.305324.MGPy8EG_N30LO_A14N23LO_DM_BBscalar_p200_c1_jpt100.EVNT.v2_EXT0/ \
  --outDS user.<grid_user_name>.mc15_13TeV.305324.MGPy8EG_N30LO_A14N23LO_DM_BBscalar_p200_c1_jpt100.DAOD_TRUTH.v2/
  --destSE INFN-NAPOLI-ATLAS_LOCALGROUPDISK
```

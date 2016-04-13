# xAOD production

GitBook allows you to organize your book into chapters, each chapter is stored in a separate file like this one.


```bash
pathena \
  --noBuild \
  --trf
    "Reco_tf.py \
     --maxEvents=-1 \
     --inputHITSFile=%IN \
     --outputAODFile=%OUT.AOD.00001.pool.root \
     --DataRunNumber=222525 \
     --DBRelease=default:current \
     --autoConfiguration=everything \
     --conditionsTag=default:OFLCOND-RUN12-SDR-31 \
     --geometryVersion=default:ATLAS-R2-2015-03-01-00 \
     --numberOfCavernBkg=0 \
     --pileupFinalBunch=6 \
     --runNumber=305323" \
  --inDS user.<grid_user_name>.mc15_13TeV.305323.MGPy8EG_N30LO_A14N23LO_DM_BBscalar_p20_c1_jpt100.SIM.v2_EXT0/ \
  --outDS user.<grid_user_name>.mc15_13TeV.305323.MGPy8EG_N30LO_A14N23LO_DM_BBscalar_p20_c1_jpt100.AOD.v3 \
  --skipScout \
  --nFilesPerJob=1 \
  --destSE INFN-NAPOLI-ATLAS_LOCALGROUPDISK
```

# DxAOD production


GitBook allows you to organize your book into chapters, each chapter is stored in a separate file like this one.


```bash
pathena --cmtConfig=x86_64-slc6-gcc48-opt --useNewTRF --trf "Reco_tf.py --inputAODFile %IN --outputDAODFile test.pool.root --ignoreErrors=True --reductionConf SUSY7 --maxEvents -1" --extOutFile DAOD_SUSY7.test.pool.root --nFilesPerJob=1 --individualOutDS --inDS user.fcirotto.mc15_13TeV.305323.MGPy8EG_N30LO_A14N23LO_DM_BBscalar_p20_c1_jpt100.AOD.v3_EXT0/ --outDS user.fcirotto.mc15_13TeV.305323.MGPy8EG_N30LO_A14N23LO_DM_BBscalar_p20_c1_jpt100.DAOD_SUSY7_p2425.v2/ --destSE INFN-NAPOLI-ATLAS_LOCALGROUPDISK
```

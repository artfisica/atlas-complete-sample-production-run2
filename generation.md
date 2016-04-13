# First Chapter: Generation

Generation of MonteCarlo Events

```bash
pathena --trf \
          "Generate_tf.py \
          --ecmEnergy=13000 \
          --firstEvent=1 \
          --randomSeed=%RNDM:1 \
          --jobConfig=MC15.305323.MGPy8EG_N30LO_A14N23LO_DM_BBscalar_p20_c1_jpt100.py \
          --outputEVNTFile=%OUT.EVNT.305323.pool.root \
          --runNumber=305323 \
          --maxEvents=1000" \
        --extFile="MadGraphControl_DMHFSimplifiedmodels_jpt100.py, \
                   MC15.305323.MGPy8EG_N30LO_A14N23LO_DM_BBscalar_p20_c1_jpt100.py" \
        --outDS user.<grid_user_name>.mc15_13TeV.305323.MGPy8EG_N30LO_A14N23LO_DM_BBscalar_p20_c1_jpt100.EVNT.v1 \
        --split 150 \
        --skipScout \
        --cloud=IT \
        --destSE INFN-NAPOLI-ATLAS_LOCALGROUPDISK
```

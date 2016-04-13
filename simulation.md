# Simulation

GitBook allows you to organize your book into chapters, each chapter is stored in a separate file like this one.

```bash
pathena --noBuild --trf "Sim_tf.py \
                           --randomSeed=%RNDM:100 \
                           --maxEvents=-1 \
                           --firstEvent=%SKIPEVENTS \
                           --inputEVNTFile=%IN \
                           --DataRunNumber=222525 \
                           --DBRelease=default:current \
                           --geometryVersion=default:ATLAS-R2-2015-03-01-00_VALIDATION \
                           --conditionsTag=default:OFLCOND-RUN12-SDR-19 \
                           --physicsList=FTFP_BERT \
                           --postInclude=default:PyJobTransforms/UseFrontier.py \
                           --preInclude=EVNTtoHITS:SimulationJobOptions/preInclude.BeamPipeKill.py \
                           --runNumber=305323 \
                           --simulator=ATLFASTII \
                           --truthStrategy=MC12 \
                           --outputHITSFile=%OUT.HITS.00001.pool.root" \
                         --inDS user.fcirotto.mc15_13TeV.305323.MGPy8EG_N30LO_A14N23LO_DM_BBscalar_p20_c1_jpt100.EVNT.v1_EXT0 \
                         --outDS user.fcirotto.mc15_13TeV.305323.MGPy8EG_N30LO_A14N23LO_DM_BBscalar_p20_c1_jpt100.SIM.v2 \
                         --skipScout \
                         --nFilesPerJob=1 \
                         --destSE INFN-NAPOLI-ATLAS_LOCALGROUPDISK
```

# Third Chapter: Reconstruction


GitBook allows you to organize your book into chapters, each chapter is stored in a separate file like this one.

```bash
usage: Reco_tf.py [-h] [--verbose]
                  [--loglevel {INFO,CRITICAL,VERBOSE,WARNING,ERROR,DEBUG,FATAL}]
                  [--argdict FILE] [--argJSON FILE] [--dumpargs] [--showGraph]
                  [--showPath] [--showSteps] [--dumpPickle FILE]
                  [--dumpJSON FILE] [--orphanKiller] [--reportName REPORTNAME]
                  [--reportType TYPE [TYPE ...]] [--execOnly]
                  [--env substep:KEY=VALUE [substep:KEY=VALUE ...]]
                  [--imf substep:BOOL [substep:BOOL ...]]
                  [--tcmalloc substep:BOOL [substep:BOOL ...]]
                  [--AMIConfig AMICONFIG] [--AMITag TAG]
                  [--steering substep:{in/out}{+-}DATA [substep:{in/out}{+-}DATA ...]]
                  [--ignoreFiles IGNOREFILES [IGNOREFILES ...]]
                  [--ignorePatterns IGNOREPATTERNS [IGNOREPATTERNS ...]]
                  [--ignoreErrors BOOL] [--checkEventCount BOOL]
                  [--skipFileValidation] [--skipInputFileValidation]
                  [--skipOutputFileValidation]
                  [--parallelFileValidation PARALLELFILEVALIDATION]
                  [--athenaopts OPT1 OPT2 OPT3] [--command COMMAND]
                  [--athena ATHENA]
                  [--preExec substep:PREEXEC [substep:PREEXEC ...]]
                  [--preInclude substep:PREINCLUDE [substep:PREINCLUDE ...]]
                  [--postExec substep:POSTEXEC [substep:POSTEXEC ...]]
                  [--postInclude substep:POSTINCLUDE [substep:POSTINCLUDE ...]]
                  [--maxEvents substep:maxEvents [substep:maxEvents ...]]
                  [--skipEvents SKIPEVENTS]
                  [--asetup substep:ASETUP [substep:ASETUP ...]]
                  [--eventAcceptanceEfficiency EVENTACCEPTANCEEFFICIENCY]
                  [--athenaMPMergeTargetSize dataType:targetSizeInMegaBytes [dataType:targetSizeInMegaBytes ...]]
                  [--valgrind substep:BOOL]
                  [--valgrindbasicopts OPT1,OPT2,OPT3]
                  [--valgrindextraopts OPT1,OPT2,OPT3]
                  [--DBRelease substep:DBRelease [substep:DBRelease ...]]
                  [--conditionsTag substep:CondTag [substep:CondTag ...]]
                  [--geometryVersion substep:GeoVersion [substep:GeoVersion ...]]
                  [--beamType BEAMTYPE] [--runNumber RUNNUMBER]
                  [--triggerConfig substep=triggerConf]
                  [--trigFilterList TRIGFILTERLIST [TRIGFILTERLIST ...]]
                  [--autoConfiguration AUTOCONFKEY [AUTOCONFKEY ...]]
                  [--trigStream TRIGSTREAM]
                  [--inputBSFile INPUTBSFILE [INPUTBSFILE ...]]
                  [--outputBSFile OUTPUTBSFILE]
                  [--inputRDOFile INPUTRDOFILE [INPUTRDOFILE ...]]
                  [--inputESDFile INPUTESDFILE [INPUTESDFILE ...]]
                  [--outputESDFile OUTPUTESDFILE]
                  [--inputAODFile INPUTAODFILE [INPUTAODFILE ...]]
                  [--outputAODFile OUTPUTAODFILE]
                  [--outputAOD_RPRFile OUTPUTAOD_RPRFILE]
                  [--outputAOD_SKIMFile OUTPUTAOD_SKIMFILE]
                  [--outputHISTFile OUTPUTHISTFILE]
                  [--outputHIST_AODFile OUTPUTHIST_AODFILE]
                  [--outputTAGFile OUTPUTTAGFILE]
                  [--inputEVNTFile INPUTEVNTFILE [INPUTEVNTFILE ...]]
                  [--outputDRAW_ZEEFile DRAW_ZEE]
                  [--outputDRAW_WENUFile DRAW_WENU]
                  [--outputDRAW_ZMUMUFile DRAW_ZMUMU]
                  [--outputDRAW_WMUNUFile DRAW_WMUNU]
                  [--outputDRAW_IDPROJCOMMFile DRAW_IDPROJCOMM]
                  [--outputDESDM_ALLCELLSFile DESDM_ALLCELLS]
                  [--outputDESDM_EGAMMAFile DESDM_EGAMMA]
                  [--outputDESD_PHOJETFile DESD_PHOJET]
                  [--outputDESD_SGLELFile DESD_SGLEL]
                  [--outputDESDM_MUONFile DESDM_MUON]
                  [--outputDESD_SGLMUFile DESD_SGLMU]
                  [--outputDESD_SLTTMUFile DESD_SLTTMU]
                  [--outputDESD_TAUMUHFile DESD_TAUMUH]
                  [--outputDESD_CALJETFile DESD_CALJET]
                  [--outputDESDM_TRACKFile DESDM_TRACK]
                  [--outputDESDM_METFile DESDM_MET]
                  [--outputDESD_MBIASFile DESD_MBIAS]
                  [--outputDESD_PRESCALEDFile DESD_PRESCALED]
                  [--outputDESD_COLLCANDFile DESD_COLLCAND]
                  [--outputD2ESD_WENUFile D2ESD_WENU]
                  [--outputD2ESD_WMUNUFile D2ESD_WMUNU]
                  [--outputD2ESD_DIPHOFile D2ESD_DIPHO]
                  [--outputDESD_PIXELCOMMFile DESD_PIXELCOMM]
                  [--outputDESD_SCTCOMMFile DESD_SCTCOMM]
                  [--outputDESD_IDCOMMFile DESD_IDCOMM]
                  [--outputDESD_IDPROJCOMMFile DESD_IDPROJCOMM]
                  [--outputDESD_CALOCOMMFile DESD_CALOCOMM]
                  [--outputDESD_TILECOMMFile DESD_TILECOMM]
                  [--outputDESD_EMCLUSCOMMFile DESD_EMCLUSCOMM]
                  [--outputDESD_EGTAUCOMMFile DESD_EGTAUCOMM]
                  [--outputDESD_RPCCOMMFile DESD_RPCCOMM]
                  [--outputDESD_TGCCOMMFile DESD_TGCCOMM]
                  [--outputDESD_MUONCOMMFile DESD_MUONCOMM]
                  [--outputDESD_RANDOMCOMMFile DESD_RANDOMCOMM]
                  [--outputDESD_HIRAREFile DESD_HIRARE]
                  [--outputDESD_SKIMELFile DESD_SKIMEL]
                  [--outputDESD_ONIAMUMUHIFile DESD_ONIAMUMUHI]
                  [--outputDESDM_RPVLLFile DESDM_RPVLL]
                  [--outputDESDM_RPVLLCCFile DESDM_RPVLLCC]
                  [--outputDESD_CTLFWJETFile DESD_CTLFWJET]
                  [--outputDESD_FWJETFile DESD_FWJET]
                  [--outputD2ESD_ZMMFile D2ESD_ZMM]
                  [--outputD2ESD_JPSIUPSMMFile D2ESD_JPSIUPSMM]
                  [--outputD2ESDM_TRKJETFile D2ESDM_TRKJET]
                  [--outputD2AOD_DIPHOFile D2AOD_DIPHO]
                  [--outputDAOD_ZEEGAMMAFile DAOD_ZEEGAMMA]
                  [--outputDAOD_ZMUMUGAMMAFile DAOD_ZMUMUGAMMA]
                  [--outputDAODM_SGLEMFile DAODM_SGLEM]
                  [--outputDAODM_SGLPHFile DAODM_SGLPH]
                  [--outputDAODM_SGLMUFile DAODM_SGLMU]
                  [--outputDAODM_SGLTAUFile DAODM_SGLTAU]
                  [--outputDAOD_2EMFile DAOD_2EM]
                  [--outputDAOD_2PHFile DAOD_2PH]
                  [--outputDAOD_2MUFile DAOD_2MU]
                  [--outputDAOD_EMMUFile DAOD_EMMU]
                  [--outputDAOD_EMTAUFile DAOD_EMTAU]
                  [--outputDAOD_MUTAUFile DAOD_MUTAU]
                  [--outputDAOD_EMMETFile DAOD_EMMET]
                  [--outputDAOD_MUMETFile DAOD_MUMET]
                  [--outputDAOD_JETMETFile DAOD_JETMET]
                  [--outputDAOD_EMJETFile DAOD_EMJET]
                  [--outputDAOD_MUJETFile DAOD_MUJET]
                  [--outputDAOD_TAUJETFile DAOD_TAUJET]
                  [--outputDAOD_SKIMELFile DAOD_SKIMEL]
                  [--outputDAOD_EGLOOSEFile DAOD_EGLOOSE]
                  [--outputDAOD_MUFile DAOD_MU]
                  [--outputDAOD_ELLOOSEFile DAOD_ELLOOSE]
                  [--outputDAOD_PHLOOSEFile DAOD_PHLOOSE]
                  [--outputDAOD_ONIAMUMUFile DAOD_ONIAMUMU]
                  [--outputDAOD_JPSIMUMUFile DAOD_JPSIMUMU]
                  [--outputDAOD_UPSIMUMUFile DAOD_UPSIMUMU]
                  [--outputDAOD_RED_TEST1File DAOD_RED_TEST1]
                  [--outputDAOD_RED_TEST2File DAOD_RED_TEST2]
                  [--outputD2AOD_DIONIAFile D2AOD_DIONIA]
                  [--outputDAOD_TESTFile DAOD_TEST]
                  [--outputD2AODM_ZEEFile D2AODM_ZEE]
                  [--outputD2AODM_ZMUMUFile D2AODM_ZMUMU]
                  [--outputD2AODM_WMUNUFile D2AODM_WMUNU]
                  [--outputD2AOD_H4LFile D2AOD_H4L]
                  [--outputDAOD_SUSYEGAMMAFile DAOD_SUSYEGAMMA]
                  [--outputDAOD_SUSYMUONSFile DAOD_SUSYMUONS]
                  [--outputDAOD_SUSYJETSFile DAOD_SUSYJETS]
                  [--outputD2AOD_ZEEFile D2AOD_ZEE]
                  [--outputD2AOD_WENUFile D2AOD_WENU]
                  [--outputDAOD_RNDMFile DAOD_RNDM]
                  [--outputDAOD_ELLOOSE18File DAOD_ELLOOSE18]
                  [--outputDAOD_H4LBREMRECFile DAOD_H4LBREMREC]
                  [--outputDAOD_HIGHMDIJETFile DAOD_HIGHMDIJET]
                  [--outputDAODM_HIGHMJJFile DAODM_HIGHMJJ]
                  [--outputDAOD_2LHSG2File DAOD_2LHSG2]
                  [--outputDAOD_4LHSG2File DAOD_4LHSG2]
                  [--outputDAOD_2L2QHSG2File DAOD_2L2QHSG2]
                  [--outputDAOD_JPSIHSG2File DAOD_JPSIHSG2]
                  [--outputDAOD_HSG1File DAOD_HSG1]
                  [--outputDAOD_HWWFile DAOD_HWW]
                  [--outputNTUP_MUONFile NTUP_MUON]
                  [--outputNTUP_PHYSICSFile NTUP_PHYSICS]
                  [--outputNTUP_COMMONFile NTUP_COMMON]
                  [--outputNTUP_SUSYLLPFile NTUP_SUSYLLP]
                  [--outputNTUP_TOPBOOSTFile NTUP_TOPBOOST]
                  [--outputNTUP_BKGDFile NTUP_BKGD]
                  [--outputNTUP_MINBIASFile NTUP_MINBIAS]
                  [--outputNTUP_TRIGFile NTUP_TRIG]
                  [--outputNTUP_TRIGMUFile NTUP_TRIGMU]
                  [--outputNTUP_L1TGCFile NTUP_L1TGC]
                  [--outputNTUP_HSG2File NTUP_HSG2]
                  [--outputNTUP_2LHSG2File NTUP_2LHSG2]
                  [--outputNTUP_TPHSG2File NTUP_TPHSG2]
                  [--outputNTUP_4LHSG2File NTUP_4LHSG2]
                  [--outputNTUP_2L2QHSG2File NTUP_2L2QHSG2]
                  [--outputNTUP_HSG5ZHMETFile NTUP_HSG5ZHMET]
                  [--outputNTUP_HSG5GAMZFile NTUP_HSG5GAMZ]
                  [--outputNTUP_HSG5ZBBFile NTUP_HSG5ZBB]
                  [--outputNTUP_HSG5WHQFile NTUP_HSG5WHQ]
                  [--outputNTUP_HSG5ZHLLUFile NTUP_HSG5ZHLLU]
                  [--outputNTUP_HSG5GAMHFile NTUP_HSG5GAMH]
                  [--outputNTUP_HSG5ZHMETUFile NTUP_HSG5ZHMETU]
                  [--outputNTUP_HSG5WHFile NTUP_HSG5WH]
                  [--outputNTUP_HSG5ZHLLFile NTUP_HSG5ZHLL]
                  [--outputNTUP_HSG5WHUFile NTUP_HSG5WHU]
                  [--outputNTUP_L1CALOPROBFile NTUP_L1CALOPROB]
                  [--outputNTUP_L1CALOFile NTUP_L1CALO]
                  [--outputNTUP_SMQCDFile NTUP_SMQCD]
                  [--outputNTUP_JETMETEMCLFile NTUP_JETMETEMCL]
                  [--outputNTUP_JETMETWZFile NTUP_JETMETWZ]
                  [--outputNTUP_JETMETFULLFile NTUP_JETMETFULL]
                  [--outputNTUP_JETMETFile NTUP_JETMET]
                  [--outputNTUP_SMZMUMUFile NTUP_SMZMUMU]
                  [--outputNTUP_SMBKGEFile NTUP_SMBKGE]
                  [--outputNTUP_SMDILEPFile NTUP_SMDILEP]
                  [--outputNTUP_SMWMUNUJJFile NTUP_SMWMUNUJJ]
                  [--outputNTUP_SMDYMUMUFile NTUP_SMDYMUMU]
                  [--outputNTUP_SMWZSOFTFile NTUP_SMWZSOFT]
                  [--outputNTUP_SMWZFile NTUP_SMWZ]
                  [--outputNTUP_SMTRILEPFile NTUP_SMTRILEP]
                  [--outputNTUP_SMWENUJJFile NTUP_SMWENUJJ]
                  [--outputNTUP_SMBKGMUFile NTUP_SMBKGMU]
                  [--outputNTUP_SMWENUFile NTUP_SMWENU]
                  [--outputNTUP_SMZEEFile NTUP_SMZEE]
                  [--outputNTUP_SMDYEEFile NTUP_SMDYEE]
                  [--outputNTUP_SMWMUNUFile NTUP_SMWMUNU]
                  [--outputNTUP_SMLIGHTFile NTUP_SMLIGHT]
                  [--outputNTUP_TAUSMALLFile NTUP_TAUSMALL]
                  [--outputNTUP_EMBLHUPFile NTUP_EMBLHUP]
                  [--outputNTUP_EMBLHIMFile NTUP_EMBLHIM]
                  [--outputNTUP_EMBHHDNFile NTUP_EMBHHDN]
                  [--outputNTUP_TAUMEDIUMFile NTUP_TAUMEDIUM]
                  [--outputNTUP_EMBLLDNFile NTUP_EMBLLDN]
                  [--outputNTUP_EMBLLIMFile NTUP_EMBLLIM]
                  [--outputNTUP_EMBHHUPFile NTUP_EMBHHUP]
                  [--outputNTUP_TAUFile NTUP_TAU]
                  [--outputNTUP_EMBLLUPFile NTUP_EMBLLUP]
                  [--outputNTUP_EMBLHDNFile NTUP_EMBLHDN]
                  [--outputNTUP_EMBHHIMFile NTUP_EMBHHIM]
                  [--outputNTUP_TAUFULLFile NTUP_TAUFULL]
                  [--outputNTUP_BTAGD3PDFile NTUP_BTAGD3PD]
                  [--outputNTUP_BTAGGHOSTFile NTUP_BTAGGHOST]
                  [--outputNTUP_BTAGFULLFile NTUP_BTAGFULL]
                  [--outputNTUP_BTAGEFFFile NTUP_BTAGEFF]
                  [--outputNTUP_BTAGSLIMFile NTUP_BTAGSLIM]
                  [--outputNTUP_ZPRIMEMMFile NTUP_ZPRIMEMM]
                  [--outputNTUP_WPRIMEMNFile NTUP_WPRIMEMN]
                  [--outputNTUP_ZPRIMEEEFile NTUP_ZPRIMEEE]
                  [--outputNTUP_WPRIMEENFile NTUP_WPRIMEEN]
                  [--outputNTUP_IDVTXLUMIFile NTUP_IDVTXLUMI]
                  [--outputNTUP_IDVTXFile NTUP_IDVTX]
                  [--outputNTUP_CLUSTERCORRECTIONFile NTUP_CLUSTERCORRECTION]
                  [--outputNTUP_EGAMMAFile NTUP_EGAMMA]
                  [--outputNTUP_TRIGBJETFile NTUP_TRIGBJET]
                  [--outputNTUP_SCTFile NTUP_SCT]
                  [--outputNTUP_MUFASTFile NTUP_MUFAST]
                  [--outputNTUP_MUONCALIBFile NTUP_MUONCALIB]
                  [--outputNTUP_TRKVALIDFile NTUP_TRKVALID]
                  [--outputNTUP_FASTMONFile NTUP_FASTMON]
                  [--outputNTUP_LARNOISEFile NTUP_LARNOISE]
                  [--outputNTUP_WZFile NTUP_WZ]
                  [--outputNTUP_TRTFile NTUP_TRT]
                  [--outputNTUP_MCPFile NTUP_MCP]
                  [--outputNTUP_HECNOISEFile NTUP_HECNOISE]
                  [--outputNTUP_ENHBIASFile NTUP_ENHBIAS]
                  [--outputNTUP_TRUTHFile NTUP_TRUTH]
                  [--outputNTUP_SUSYTRUTHFile NTUP_SUSYTRUTH]
                  [--outputNTUP_HIGHMULTFile NTUP_HIGHMULT]
                  [--outputNTUP_PROMPTPHOTFile NTUP_PROMPTPHOT]
                  [--outputDESDM_BEAMSPOTFile DESDM_BEAMSPOT]
                  [--outputDAOD_HSG2File DAOD_HSG2]
                  [--inputNTUP_COMMONFile INPUTNTUP_COMMONFILE [INPUTNTUP_COMMONFILE ...]]
                  [--outputDNTUPFile OUTPUTDNTUPFILE]
                  [--outputDAODFile OUTPUTDAODFILE]
                  [--reductionConf REDUCTIONCONF [REDUCTIONCONF ...]]
                  [--passThrough True/False]
                  [--inputHITSFile INPUTHITSFILE [INPUTHITSFILE ...]]
                  [--outputRDOFile OUTPUTRDOFILE [OUTPUTRDOFILE ...]]
                  [--outputRDO_FILTFile OUTPUTRDO_FILTFILE [OUTPUTRDO_FILTFILE ...]]
                  [--digiSeedOffset1 DIGISEEDOFFSET1]
                  [--digiSeedOffset2 DIGISEEDOFFSET2]
                  [--digiRndmSvc DIGIRNDMSVC]
                  [--digiSteeringConf DIGISTEERINGCONF]
                  [--samplingFractionDbTag SAMPLINGFRACTIONDBTAG]
                  [--doAllNoise DOALLNOISE] [--AddCaloDigi ADDCALODIGI]
                  [--LucidOn LUCIDON] [--AFPOn AFPON] [--ALFAOn ALFAON]
                  [--ZDCOn ZDCON] [--FwdRegionOn FWDREGIONON]
                  [--testPileUpConfig TESTPILEUPCONFIG]
                  [--inputLowPtMinbiasHitsFile INPUTLOWPTMINBIASHITSFILE [INPUTLOWPTMINBIASHITSFILE ...]]
                  [--inputHighPtMinbiasHitsFile INPUTHIGHPTMINBIASHITSFILE [INPUTHIGHPTMINBIASHITSFILE ...]]
                  [--inputCavernHitsFile INPUTCAVERNHITSFILE [INPUTCAVERNHITSFILE ...]]
                  [--inputBeamHaloHitsFile INPUTBEAMHALOHITSFILE [INPUTBEAMHALOHITSFILE ...]]
                  [--inputBeamGasHitsFile INPUTBEAMGASHITSFILE [INPUTBEAMGASHITSFILE ...]]
                  [--numberOfLowPtMinBias NUMBEROFLOWPTMINBIAS]
                  [--numberOfHighPtMinBias NUMBEROFHIGHPTMINBIAS]
                  [--numberOfBeamHalo NUMBEROFBEAMHALO]
                  [--numberOfBeamGas NUMBEROFBEAMGAS]
                  [--numberOfCavernBkg NUMBEROFCAVERNBKG]
                  [--bunchSpacing BUNCHSPACING]
                  [--pileupInitialBunch PILEUPINITIALBUNCH]
                  [--pileupFinalBunch PILEUPFINALBUNCH]
                  [--DataRunNumber DATARUNNUMBER] [--jobNumber JOBNUMBER]
                  [--outputNTUP_PHYSVALFile OUTPUTNTUP_PHYSVALFILE]
                  [--validationFlags VALIDATIONFLAGS [VALIDATIONFLAGS ...]]

Transform Reco_tf. General purpose ATLAS reconstruction transform, which also
supports digitisation. Inputs can be HITS, RDO, BS, ESD or AOD, with outputs
of RDO, ESD, AOD or DPDs. See
https://twiki.cern.ch/twiki/bin/view/AtlasComputing/RecoTf for more details.

optional arguments:
  -h, --help            show this help message and exit
  --verbose, --debug    Set transform loglevel to DEBUG
  --loglevel {INFO,CRITICAL,VERBOSE,WARNING,ERROR,DEBUG,FATAL}
                        Set transform logging level
  --argdict FILE        File containing pickled argument dictionary
  --argJSON FILE, --argjson FILE
                        File containing JSON serialised argument dictionary
  --dumpargs            Dump transform arguments and exit
  --showGraph           Show multi-step transform graph, then exit
  --showPath            Show execution path only, then exit
  --showSteps           Show list of executor steps only, then exit
  --dumpPickle FILE     Interpret command line arguments and write them out as
                        a pickle file
  --dumpJSON FILE       Interpret command line arguments and write them out as
                        a JSON file
  --orphanKiller        Kill all orphaned children at the end of a job (that
                        is, sharing the transform's pgid, but with
                        ppid=1).Beware, this is potentially dangerous in a a
                        batch environment
  --reportName REPORTNAME
                        Base name for job reports (default name is "jobReport"
                        for most reports, but "metadata" for classic prodsys
                        XML)
  --reportType TYPE [TYPE ...]
                        Job reports to produce: valid values are "text",
                        "json", "classic", "pilotPickle" and "gpickle"
  --execOnly            Exec the first substep only, replacing the transform
                        process (no job reports and the return code will be
                        from the substep process)
  --env substep:KEY=VALUE [substep:KEY=VALUE ...]
                        Explicitly set environment variables for an executor
                        (default is all substeps). N.B. this setting is passed
                        to the shell, so reference to shell variables is
                        allowed, e.g. KEY=VALUE:$KEY
  --imf substep:BOOL [substep:BOOL ...]
                        Manually include/exclude the Intel IMF maths library
                        (otherwise this is disabled for base releases < 17.7,
                        enabled otherwise)
  --tcmalloc substep:BOOL [substep:BOOL ...]
                        Switch preload of the tcmalloc library (disabled by
                        default)
  --AMIConfig AMICONFIG, --amiConfig AMICONFIG, --AMI AMICONFIG
                        Configure transform with AMI tag
  --AMITag TAG, --amiConfigTag TAG, --AMIConfigTag TAG
                        AMI tag from which this job was defined - this option
                        simply writes the relevant AMI tag value into the
                        output metadata, it does not configure the job (use
                        --AMIConfig for that)
  --steering substep:{in/out}{+-}DATA [substep:{in/out}{+-}DATA ...]
                        Steer the transform by manipulating the execution
                        graph before the execution path is calculated. Format
                        is substep:{in,out}{+-}DATA,{in,out}{+-}DATA,... to
                        modify the substep's input/output by adding/removing a
                        data type. e.g. RAWtoESD:in-RDO,in+RDO_TRIG would
                        remove RDO and add RDO_TRIG to the list of valid input
                        datatypes for the RAWtoESD substep.
  --eventAcceptanceEfficiency EVENTACCEPTANCEEFFICIENCY
                        Allowed "efficiency" for processing events - used to
                        ensure output file has enough events (default 1.0)
  --athenaMPMergeTargetSize dataType:targetSizeInMegaBytes [dataType:targetSizeInMegaBytes ...], --mts dataType:targetSizeInMegaBytes [dataType:targetSizeInMegaBytes ...]
                        Set the target merge size for an AthenaMP output file
                        type (give size in MB). Note that the special value 0
                        means do not merge this output file; negative values
                        means always merge to a single file. Note that the
                        datatype "ALL" will be used as a default for all
                        datatypes not explicitly given their own value.
  --passThrough True/False
                        Run the derivation framework in a pass-through mode,
                        needed for some MC samples. Needs to be implemented in
                        derivation JOs

Validation:
  Standard job validation switches

  --ignoreFiles IGNOREFILES [IGNOREFILES ...], --ignoreFilters IGNOREFILES [IGNOREFILES ...]
                        Files containing error patterns to be ignored during
                        logfile scans (will split on commas; use "None" to
                        disable the standard "atlas_error_mask.db")
  --ignorePatterns IGNOREPATTERNS [IGNOREPATTERNS ...]
                        Regexp error patterns to be ignored during logfile
                        scans (will be applied as a search against the whole
                        logfile line)
  --ignoreErrors BOOL   Ignore ERROR lines in logfiles (use with care this can
                        mask serious problems; --ignorePatterns is prefered)
  --checkEventCount BOOL
                        Enable check of output events against input events
                        (default: True)

File Validation:
  Standard file validation switches

  --skipFileValidation, --omitFileValidation
                        Skip both input and output file validation (warning -
                        do not use this option in production jobs!)
  --skipInputFileValidation, --omitInputFileValidation
                        Skip input file validation (warning - do not use this
                        option in production jobs!)
  --skipOutputFileValidation, --omitOutputFileValidation
                        Skip output file validation (warning - do not use this
                        option in production jobs!)
  --parallelFileValidation PARALLELFILEVALIDATION
                        Parallelise file validation

Athena:
  General Athena Options

  --athenaopts OPT1 OPT2 OPT3
                        Extra options to pass to athena. Will split on spaces.
                        Options starting with "-" must be given as
                        --athenaopts='--opt1 --opt2[=foo] ...'
  --command COMMAND, -c COMMAND
                        Run COMMAND before all else
  --athena ATHENA       Use ATHENA as the athena executable
  --preExec substep:PREEXEC [substep:PREEXEC ...]
                        Python code to execute before main job options are
                        included (can be optionally limited to a single
                        substep)
  --preInclude substep:PREINCLUDE [substep:PREINCLUDE ...]
                        Python configuration fragment to include before main
                        job options (can be optionally limited to a single
                        substep). Will split on commas: frag1.py,frag2.py is
                        understood.
  --postExec substep:POSTEXEC [substep:POSTEXEC ...]
                        Python code to execute after main job options are
                        included (can be optionally limited to a single
                        substep)
  --postInclude substep:POSTINCLUDE [substep:POSTINCLUDE ...]
                        Python configuration fragment to include after main
                        job options (can be optionally limited to a single
                        substep). Will split on commas: frag1.py,frag2.py is
                        understood.
  --maxEvents substep:maxEvents [substep:maxEvents ...]
                        Set maximum events for each processing step (default
                        substep is "first")
  --skipEvents SKIPEVENTS
                        Number of events to skip over in the first processing
                        step
  --asetup substep:ASETUP [substep:ASETUP ...]
                        asetup command string to be run before this substep is
                        executed

Valgrind:
  General Valgrind Options

  --valgrind substep:BOOL
                        Enable Valgrind
  --valgrindbasicopts OPT1,OPT2,OPT3
                        Basic options passed to Valgrind when running Athena.
                        Options starting with "-" must be given as
                        --valgrindopts='--opt1=foo,--opt2=bar,...'
  --valgrindextraopts OPT1,OPT2,OPT3
                        Extra options passed to Valgrind when running Athena.
                        Options starting with "-" must be given as
                        --valgrindopts='--opt1=foo,--opt2=bar,...'

Detector:
  General detector configuration options, for simulation and reconstruction

  --DBRelease substep:DBRelease [substep:DBRelease ...]
                        Use DBRelease instead of ORACLE. Give either a
                        DBRelease tarball file (e.g., DBRelease-21.7.1.tar.gz)
                        or cvmfs DBRelease directory (e.g., 21.7.1 or current
  --conditionsTag substep:CondTag [substep:CondTag ...]
                        Conditions tag to set
  --geometryVersion substep:GeoVersion [substep:GeoVersion ...]
                        ATLAS geometry version tag
  --beamType BEAMTYPE   Manual beam type setting
  --runNumber RUNNUMBER, --RunNumber RUNNUMBER
                        Manual run number setting

Trigger:
  Trigger Related Options

  --triggerConfig substep=triggerConf
                        Trigger configuration string (substep aware argument -
                        default is to run trigger in RAWtoESD step, use syntax
                        SUBSTEP=TRIGCONF if you want to run trigger somewhere
                        else). N.B. This argument uses EQUALS (=) to separate
                        the substep name from the value.
  --trigFilterList TRIGFILTERLIST [TRIGFILTERLIST ...]
                        Trigger filter list (multiple values can be given
                        separately or split on commas; only understood in
                        RAWtoESD)

Common Reco:
  Common Reconstruction Options

  --autoConfiguration AUTOCONFKEY [AUTOCONFKEY ...]
                        Autoconfiguration settings (whitespace or comma
                        separated)
  --trigStream TRIGSTREAM
                        Trigger stream setting

Reco Files:
  Reconstruction file options

  --inputBSFile INPUTBSFILE [INPUTBSFILE ...]
                        Input bytestream file
  --outputBSFile OUTPUTBSFILE
                        Output bytestream file
  --inputRDOFile INPUTRDOFILE [INPUTRDOFILE ...]
                        Input RDO file
  --inputESDFile INPUTESDFILE [INPUTESDFILE ...]
                        Input ESD file
  --outputESDFile OUTPUTESDFILE
                        Output ESD file
  --inputAODFile INPUTAODFILE [INPUTAODFILE ...]
                        Input AOD file
  --outputAODFile OUTPUTAODFILE
                        Output AOD file
  --outputAOD_RPRFile OUTPUTAOD_RPRFILE
                        Output AOD (reprocessed) file
  --outputAOD_SKIMFile OUTPUTAOD_SKIMFILE
                        Output skimmed AOD file
  --outputHISTFile OUTPUTHISTFILE
                        Output DQ monitoring file
  --outputHIST_AODFile OUTPUTHIST_AODFILE
                        Output DQ monitoring file
  --outputTAGFile OUTPUTTAGFILE
                        Output TAG file
  --inputEVNTFile INPUTEVNTFILE [INPUTEVNTFILE ...]
                        Input EVNT file for NTUP_TRUTH making

Primary DPDs:
  Primary DPD File Options

  --outputDRAW_ZEEFile DRAW_ZEE
                        DPD DRAW output DRAW_ZEE file
  --outputDRAW_WENUFile DRAW_WENU
                        DPD DRAW output DRAW_WENU file
  --outputDRAW_ZMUMUFile DRAW_ZMUMU
                        DPD DRAW output DRAW_ZMUMU file
  --outputDRAW_WMUNUFile DRAW_WMUNU
                        DPD DRAW output DRAW_WMUNU file
  --outputDRAW_IDPROJCOMMFile DRAW_IDPROJCOMM
                        DPD DRAW output DRAW_IDPROJCOMM file
  --outputDESDM_ALLCELLSFile DESDM_ALLCELLS
                        DPD DESDM output DESDM_ALLCELLS file
  --outputDESDM_EGAMMAFile DESDM_EGAMMA
                        DPD DESDM output DESDM_EGAMMA file
  --outputDESD_PHOJETFile DESD_PHOJET
                        DPD DESD output DESD_PHOJET file
  --outputDESD_SGLELFile DESD_SGLEL
                        DPD DESD output DESD_SGLEL file
  --outputDESDM_MUONFile DESDM_MUON
                        DPD DESDM output DESDM_MUON file
  --outputDESD_SGLMUFile DESD_SGLMU
                        DPD DESD output DESD_SGLMU file
  --outputDESD_SLTTMUFile DESD_SLTTMU
                        DPD DESD output DESD_SLTTMU file
  --outputDESD_TAUMUHFile DESD_TAUMUH
                        DPD DESD output DESD_TAUMUH file
  --outputDESD_CALJETFile DESD_CALJET
                        DPD DESD output DESD_CALJET file
  --outputDESDM_TRACKFile DESDM_TRACK
                        DPD DESDM output DESDM_TRACK file
  --outputDESDM_METFile DESDM_MET
                        DPD DESDM output DESDM_MET file
  --outputDESD_MBIASFile DESD_MBIAS
                        DPD DESD output DESD_MBIAS file
  --outputDESD_PRESCALEDFile DESD_PRESCALED
                        DPD DESD output DESD_PRESCALED file
  --outputDESD_COLLCANDFile DESD_COLLCAND
                        DPD DESD output DESD_COLLCAND file
  --outputD2ESD_WENUFile D2ESD_WENU
                        DPD D2ESD output D2ESD_WENU file
  --outputD2ESD_WMUNUFile D2ESD_WMUNU
                        DPD D2ESD output D2ESD_WMUNU file
  --outputD2ESD_DIPHOFile D2ESD_DIPHO
                        DPD D2ESD output D2ESD_DIPHO file
  --outputDESD_PIXELCOMMFile DESD_PIXELCOMM
                        DPD DESD output DESD_PIXELCOMM file
  --outputDESD_SCTCOMMFile DESD_SCTCOMM
                        DPD DESD output DESD_SCTCOMM file
  --outputDESD_IDCOMMFile DESD_IDCOMM
                        DPD DESD output DESD_IDCOMM file
  --outputDESD_IDPROJCOMMFile DESD_IDPROJCOMM
                        DPD DESD output DESD_IDPROJCOMM file
  --outputDESD_CALOCOMMFile DESD_CALOCOMM
                        DPD DESD output DESD_CALOCOMM file
  --outputDESD_TILECOMMFile DESD_TILECOMM
                        DPD DESD output DESD_TILECOMM file
  --outputDESD_EMCLUSCOMMFile DESD_EMCLUSCOMM
                        DPD DESD output DESD_EMCLUSCOMM file
  --outputDESD_EGTAUCOMMFile DESD_EGTAUCOMM
                        DPD DESD output DESD_EGTAUCOMM file
  --outputDESD_RPCCOMMFile DESD_RPCCOMM
                        DPD DESD output DESD_RPCCOMM file
  --outputDESD_TGCCOMMFile DESD_TGCCOMM
                        DPD DESD output DESD_TGCCOMM file
  --outputDESD_MUONCOMMFile DESD_MUONCOMM
                        DPD DESD output DESD_MUONCOMM file
  --outputDESD_RANDOMCOMMFile DESD_RANDOMCOMM
                        DPD DESD output DESD_RANDOMCOMM file
  --outputDESD_HIRAREFile DESD_HIRARE
                        DPD DESD output DESD_HIRARE file
  --outputDESD_SKIMELFile DESD_SKIMEL
                        DPD DESD output DESD_SKIMEL file
  --outputDESD_ONIAMUMUHIFile DESD_ONIAMUMUHI
                        DPD DESD output DESD_ONIAMUMUHI file
  --outputDESDM_RPVLLFile DESDM_RPVLL
                        DPD DESDM output DESDM_RPVLL file
  --outputDESDM_RPVLLCCFile DESDM_RPVLLCC
                        DPD DESDM output DESDM_RPVLLCC file
  --outputDESD_CTLFWJETFile DESD_CTLFWJET
                        DPD DESD output DESD_CTLFWJET file
  --outputDESD_FWJETFile DESD_FWJET
                        DPD DESD output DESD_FWJET file
  --outputD2ESD_ZMMFile D2ESD_ZMM
                        DPD D2ESD output D2ESD_ZMM file
  --outputD2ESD_JPSIUPSMMFile D2ESD_JPSIUPSMM
                        DPD D2ESD output D2ESD_JPSIUPSMM file
  --outputD2ESDM_TRKJETFile D2ESDM_TRKJET
                        DPD D2ESDM output D2ESDM_TRKJET file
  --outputD2AOD_DIPHOFile D2AOD_DIPHO
                        DPD D2AOD output D2AOD_DIPHO file
  --outputDAOD_ZEEGAMMAFile DAOD_ZEEGAMMA
                        DPD DAOD output DAOD_ZEEGAMMA file
  --outputDAOD_ZMUMUGAMMAFile DAOD_ZMUMUGAMMA
                        DPD DAOD output DAOD_ZMUMUGAMMA file
  --outputDAODM_SGLEMFile DAODM_SGLEM
                        DPD DAODM output DAODM_SGLEM file
  --outputDAODM_SGLPHFile DAODM_SGLPH
                        DPD DAODM output DAODM_SGLPH file
  --outputDAODM_SGLMUFile DAODM_SGLMU
                        DPD DAODM output DAODM_SGLMU file
  --outputDAODM_SGLTAUFile DAODM_SGLTAU
                        DPD DAODM output DAODM_SGLTAU file
  --outputDAOD_2EMFile DAOD_2EM
                        DPD DAOD output DAOD_2EM file
  --outputDAOD_2PHFile DAOD_2PH
                        DPD DAOD output DAOD_2PH file
  --outputDAOD_2MUFile DAOD_2MU
                        DPD DAOD output DAOD_2MU file
  --outputDAOD_EMMUFile DAOD_EMMU
                        DPD DAOD output DAOD_EMMU file
  --outputDAOD_EMTAUFile DAOD_EMTAU
                        DPD DAOD output DAOD_EMTAU file
  --outputDAOD_MUTAUFile DAOD_MUTAU
                        DPD DAOD output DAOD_MUTAU file
  --outputDAOD_EMMETFile DAOD_EMMET
                        DPD DAOD output DAOD_EMMET file
  --outputDAOD_MUMETFile DAOD_MUMET
                        DPD DAOD output DAOD_MUMET file
  --outputDAOD_JETMETFile DAOD_JETMET
                        DPD DAOD output DAOD_JETMET file
  --outputDAOD_EMJETFile DAOD_EMJET
                        DPD DAOD output DAOD_EMJET file
  --outputDAOD_MUJETFile DAOD_MUJET
                        DPD DAOD output DAOD_MUJET file
  --outputDAOD_TAUJETFile DAOD_TAUJET
                        DPD DAOD output DAOD_TAUJET file
  --outputDAOD_SKIMELFile DAOD_SKIMEL
                        DPD DAOD output DAOD_SKIMEL file
  --outputDAOD_EGLOOSEFile DAOD_EGLOOSE
                        DPD DAOD output DAOD_EGLOOSE file
  --outputDAOD_MUFile DAOD_MU
                        DPD DAOD output DAOD_MU file
  --outputDAOD_ELLOOSEFile DAOD_ELLOOSE
                        DPD DAOD output DAOD_ELLOOSE file
  --outputDAOD_PHLOOSEFile DAOD_PHLOOSE
                        DPD DAOD output DAOD_PHLOOSE file
  --outputDAOD_ONIAMUMUFile DAOD_ONIAMUMU
                        DPD DAOD output DAOD_ONIAMUMU file
  --outputDAOD_JPSIMUMUFile DAOD_JPSIMUMU
                        DPD DAOD output DAOD_JPSIMUMU file
  --outputDAOD_UPSIMUMUFile DAOD_UPSIMUMU
                        DPD DAOD output DAOD_UPSIMUMU file
  --outputDAOD_RED_TEST1File DAOD_RED_TEST1
                        DPD DAOD output DAOD_RED_TEST1 file
  --outputDAOD_RED_TEST2File DAOD_RED_TEST2
                        DPD DAOD output DAOD_RED_TEST2 file
  --outputD2AOD_DIONIAFile D2AOD_DIONIA
                        DPD D2AOD output D2AOD_DIONIA file
  --outputDAOD_TESTFile DAOD_TEST
                        DPD DAOD output DAOD_TEST file
  --outputD2AODM_ZEEFile D2AODM_ZEE
                        DPD D2AODM output D2AODM_ZEE file
  --outputD2AODM_ZMUMUFile D2AODM_ZMUMU
                        DPD D2AODM output D2AODM_ZMUMU file
  --outputD2AODM_WMUNUFile D2AODM_WMUNU
                        DPD D2AODM output D2AODM_WMUNU file
  --outputD2AOD_H4LFile D2AOD_H4L
                        DPD D2AOD output D2AOD_H4L file
  --outputDAOD_SUSYEGAMMAFile DAOD_SUSYEGAMMA
                        DPD DAOD output DAOD_SUSYEGAMMA file
  --outputDAOD_SUSYMUONSFile DAOD_SUSYMUONS
                        DPD DAOD output DAOD_SUSYMUONS file
  --outputDAOD_SUSYJETSFile DAOD_SUSYJETS
                        DPD DAOD output DAOD_SUSYJETS file
  --outputD2AOD_ZEEFile D2AOD_ZEE
                        DPD D2AOD output D2AOD_ZEE file
  --outputD2AOD_WENUFile D2AOD_WENU
                        DPD D2AOD output D2AOD_WENU file
  --outputDAOD_RNDMFile DAOD_RNDM
                        DPD DAOD output DAOD_RNDM file
  --outputDAOD_ELLOOSE18File DAOD_ELLOOSE18
                        DPD DAOD output DAOD_ELLOOSE18 file
  --outputDAOD_H4LBREMRECFile DAOD_H4LBREMREC
                        DPD DAOD output DAOD_H4LBREMREC file
  --outputDAOD_HIGHMDIJETFile DAOD_HIGHMDIJET
                        DPD DAOD output DAOD_HIGHMDIJET file
  --outputDAODM_HIGHMJJFile DAODM_HIGHMJJ
                        DPD DAODM output DAODM_HIGHMJJ file
  --outputDAOD_2LHSG2File DAOD_2LHSG2
                        DPD DAOD output DAOD_2LHSG2 file
  --outputDAOD_4LHSG2File DAOD_4LHSG2
                        DPD DAOD output DAOD_4LHSG2 file
  --outputDAOD_2L2QHSG2File DAOD_2L2QHSG2
                        DPD DAOD output DAOD_2L2QHSG2 file
  --outputDAOD_JPSIHSG2File DAOD_JPSIHSG2
                        DPD DAOD output DAOD_JPSIHSG2 file
  --outputDAOD_HSG1File DAOD_HSG1
                        DPD DAOD output DAOD_HSG1 file
  --outputDAOD_HWWFile DAOD_HWW
                        DPD DAOD output DAOD_HWW file

D3PD NTUPs:
  D3PD File Options

  --outputNTUP_MUONFile NTUP_MUON
                        D3PD output NTUP_MUON file (can be made in substeps
                        a2d,e2d)
  --outputNTUP_PHYSICSFile NTUP_PHYSICS
                        D3PD output NTUP_PHYSICS file (can be made in substeps
                        a2d,e2d)
  --outputNTUP_COMMONFile NTUP_COMMON
                        D3PD output NTUP_COMMON file (can be made in substeps
                        a2d,e2d)
  --outputNTUP_SUSYLLPFile NTUP_SUSYLLP
                        D3PD output NTUP_SUSYLLP file (can be made in substeps
                        a2d,e2d)
  --outputNTUP_TOPBOOSTFile NTUP_TOPBOOST
                        D3PD output NTUP_TOPBOOST file (can be made in
                        substeps a2d,e2d)
  --outputNTUP_BKGDFile NTUP_BKGD
                        D3PD output NTUP_BKGD file (can be made in substeps
                        e2d,a2d)
  --outputNTUP_MINBIASFile NTUP_MINBIAS
                        D3PD output NTUP_MINBIAS file (can be made in substeps
                        e2d)
  --outputNTUP_TRIGFile NTUP_TRIG
                        D3PD output NTUP_TRIG file (can be made in substeps
                        e2d,a2d)
  --outputNTUP_TRIGMUFile NTUP_TRIGMU
                        D3PD output NTUP_TRIGMU file (can be made in substeps
                        e2d,a2d)
  --outputNTUP_L1TGCFile NTUP_L1TGC
                        D3PD output NTUP_L1TGC file (can be made in substeps
                        e2d)
  --outputNTUP_HSG2File NTUP_HSG2
                        D3PD output NTUP_HSG2 file (can be made in substeps
                        a2d,e2d)
  --outputNTUP_2LHSG2File NTUP_2LHSG2
                        D3PD output NTUP_2LHSG2 file (can be made in substeps
                        a2d,e2d)
  --outputNTUP_TPHSG2File NTUP_TPHSG2
                        D3PD output NTUP_TPHSG2 file (can be made in substeps
                        a2d,e2d)
  --outputNTUP_4LHSG2File NTUP_4LHSG2
                        D3PD output NTUP_4LHSG2 file (can be made in substeps
                        a2d,e2d)
  --outputNTUP_2L2QHSG2File NTUP_2L2QHSG2
                        D3PD output NTUP_2L2QHSG2 file (can be made in
                        substeps a2d,e2d)
  --outputNTUP_HSG5ZHMETFile NTUP_HSG5ZHMET
                        D3PD output NTUP_HSG5ZHMET file (can be made in
                        substeps a2d,e2d)
  --outputNTUP_HSG5GAMZFile NTUP_HSG5GAMZ
                        D3PD output NTUP_HSG5GAMZ file (can be made in
                        substeps a2d,e2d)
  --outputNTUP_HSG5ZBBFile NTUP_HSG5ZBB
                        D3PD output NTUP_HSG5ZBB file (can be made in substeps
                        a2d,e2d)
  --outputNTUP_HSG5WHQFile NTUP_HSG5WHQ
                        D3PD output NTUP_HSG5WHQ file (can be made in substeps
                        a2d,e2d)
  --outputNTUP_HSG5ZHLLUFile NTUP_HSG5ZHLLU
                        D3PD output NTUP_HSG5ZHLLU file (can be made in
                        substeps a2d,e2d)
  --outputNTUP_HSG5GAMHFile NTUP_HSG5GAMH
                        D3PD output NTUP_HSG5GAMH file (can be made in
                        substeps a2d,e2d)
  --outputNTUP_HSG5ZHMETUFile NTUP_HSG5ZHMETU
                        D3PD output NTUP_HSG5ZHMETU file (can be made in
                        substeps a2d,e2d)
  --outputNTUP_HSG5WHFile NTUP_HSG5WH
                        D3PD output NTUP_HSG5WH file (can be made in substeps
                        a2d,e2d)
  --outputNTUP_HSG5ZHLLFile NTUP_HSG5ZHLL
                        D3PD output NTUP_HSG5ZHLL file (can be made in
                        substeps a2d,e2d)
  --outputNTUP_HSG5WHUFile NTUP_HSG5WHU
                        D3PD output NTUP_HSG5WHU file (can be made in substeps
                        a2d,e2d)
  --outputNTUP_L1CALOPROBFile NTUP_L1CALOPROB
                        D3PD output NTUP_L1CALOPROB file (can be made in
                        substeps e2d)
  --outputNTUP_L1CALOFile NTUP_L1CALO
                        D3PD output NTUP_L1CALO file (can be made in substeps
                        e2d)
  --outputNTUP_SMQCDFile NTUP_SMQCD
                        D3PD output NTUP_SMQCD file (can be made in substeps
                        a2d,e2d)
  --outputNTUP_JETMETEMCLFile NTUP_JETMETEMCL
                        D3PD output NTUP_JETMETEMCL file (can be made in
                        substeps a2d,e2d)
  --outputNTUP_JETMETWZFile NTUP_JETMETWZ
                        D3PD output NTUP_JETMETWZ file (can be made in
                        substeps a2d,e2d)
  --outputNTUP_JETMETFULLFile NTUP_JETMETFULL
                        D3PD output NTUP_JETMETFULL file (can be made in
                        substeps a2d,e2d)
  --outputNTUP_JETMETFile NTUP_JETMET
                        D3PD output NTUP_JETMET file (can be made in substeps
                        a2d,e2d)
  --outputNTUP_SMZMUMUFile NTUP_SMZMUMU
                        D3PD output NTUP_SMZMUMU file (can be made in substeps
                        a2d,e2d)
  --outputNTUP_SMBKGEFile NTUP_SMBKGE
                        D3PD output NTUP_SMBKGE file (can be made in substeps
                        a2d,e2d)
  --outputNTUP_SMDILEPFile NTUP_SMDILEP
                        D3PD output NTUP_SMDILEP file (can be made in substeps
                        a2d,e2d)
  --outputNTUP_SMWMUNUJJFile NTUP_SMWMUNUJJ
                        D3PD output NTUP_SMWMUNUJJ file (can be made in
                        substeps a2d,e2d)
  --outputNTUP_SMDYMUMUFile NTUP_SMDYMUMU
                        D3PD output NTUP_SMDYMUMU file (can be made in
                        substeps a2d,e2d)
  --outputNTUP_SMWZSOFTFile NTUP_SMWZSOFT
                        D3PD output NTUP_SMWZSOFT file (can be made in
                        substeps a2d,e2d)
  --outputNTUP_SMWZFile NTUP_SMWZ
                        D3PD output NTUP_SMWZ file (can be made in substeps
                        a2d,e2d)
  --outputNTUP_SMTRILEPFile NTUP_SMTRILEP
                        D3PD output NTUP_SMTRILEP file (can be made in
                        substeps a2d,e2d)
  --outputNTUP_SMWENUJJFile NTUP_SMWENUJJ
                        D3PD output NTUP_SMWENUJJ file (can be made in
                        substeps a2d,e2d)
  --outputNTUP_SMBKGMUFile NTUP_SMBKGMU
                        D3PD output NTUP_SMBKGMU file (can be made in substeps
                        a2d,e2d)
  --outputNTUP_SMWENUFile NTUP_SMWENU
                        D3PD output NTUP_SMWENU file (can be made in substeps
                        a2d,e2d)
  --outputNTUP_SMZEEFile NTUP_SMZEE
                        D3PD output NTUP_SMZEE file (can be made in substeps
                        a2d,e2d)
  --outputNTUP_SMDYEEFile NTUP_SMDYEE
                        D3PD output NTUP_SMDYEE file (can be made in substeps
                        a2d,e2d)
  --outputNTUP_SMWMUNUFile NTUP_SMWMUNU
                        D3PD output NTUP_SMWMUNU file (can be made in substeps
                        a2d,e2d)
  --outputNTUP_SMLIGHTFile NTUP_SMLIGHT
                        D3PD output NTUP_SMLIGHT file (can be made in substeps
                        a2d,e2d)
  --outputNTUP_TAUSMALLFile NTUP_TAUSMALL
                        D3PD output NTUP_TAUSMALL file (can be made in
                        substeps a2d,e2d)
  --outputNTUP_EMBLHUPFile NTUP_EMBLHUP
                        D3PD output NTUP_EMBLHUP file (can be made in substeps
                        a2d,e2d)
  --outputNTUP_EMBLHIMFile NTUP_EMBLHIM
                        D3PD output NTUP_EMBLHIM file (can be made in substeps
                        a2d,e2d)
  --outputNTUP_EMBHHDNFile NTUP_EMBHHDN
                        D3PD output NTUP_EMBHHDN file (can be made in substeps
                        a2d,e2d)
  --outputNTUP_TAUMEDIUMFile NTUP_TAUMEDIUM
                        D3PD output NTUP_TAUMEDIUM file (can be made in
                        substeps a2d,e2d)
  --outputNTUP_EMBLLDNFile NTUP_EMBLLDN
                        D3PD output NTUP_EMBLLDN file (can be made in substeps
                        a2d,e2d)
  --outputNTUP_EMBLLIMFile NTUP_EMBLLIM
                        D3PD output NTUP_EMBLLIM file (can be made in substeps
                        a2d,e2d)
  --outputNTUP_EMBHHUPFile NTUP_EMBHHUP
                        D3PD output NTUP_EMBHHUP file (can be made in substeps
                        a2d,e2d)
  --outputNTUP_TAUFile NTUP_TAU
                        D3PD output NTUP_TAU file (can be made in substeps
                        a2d,e2d)
  --outputNTUP_EMBLLUPFile NTUP_EMBLLUP
                        D3PD output NTUP_EMBLLUP file (can be made in substeps
                        a2d,e2d)
  --outputNTUP_EMBLHDNFile NTUP_EMBLHDN
                        D3PD output NTUP_EMBLHDN file (can be made in substeps
                        a2d,e2d)
  --outputNTUP_EMBHHIMFile NTUP_EMBHHIM
                        D3PD output NTUP_EMBHHIM file (can be made in substeps
                        a2d,e2d)
  --outputNTUP_TAUFULLFile NTUP_TAUFULL
                        D3PD output NTUP_TAUFULL file (can be made in substeps
                        a2d,e2d)
  --outputNTUP_BTAGD3PDFile NTUP_BTAGD3PD
                        D3PD output NTUP_BTAGD3PD file (can be made in
                        substeps a2d,e2d)
  --outputNTUP_BTAGGHOSTFile NTUP_BTAGGHOST
                        D3PD output NTUP_BTAGGHOST file (can be made in
                        substeps a2d,e2d)
  --outputNTUP_BTAGFULLFile NTUP_BTAGFULL
                        D3PD output NTUP_BTAGFULL file (can be made in
                        substeps a2d,e2d)
  --outputNTUP_BTAGEFFFile NTUP_BTAGEFF
                        D3PD output NTUP_BTAGEFF file (can be made in substeps
                        a2d,e2d)
  --outputNTUP_BTAGSLIMFile NTUP_BTAGSLIM
                        D3PD output NTUP_BTAGSLIM file (can be made in
                        substeps a2d,e2d)
  --outputNTUP_ZPRIMEMMFile NTUP_ZPRIMEMM
                        D3PD output NTUP_ZPRIMEMM file (can be made in
                        substeps a2d,e2d)
  --outputNTUP_WPRIMEMNFile NTUP_WPRIMEMN
                        D3PD output NTUP_WPRIMEMN file (can be made in
                        substeps a2d,e2d)
  --outputNTUP_ZPRIMEEEFile NTUP_ZPRIMEEE
                        D3PD output NTUP_ZPRIMEEE file (can be made in
                        substeps a2d,e2d)
  --outputNTUP_WPRIMEENFile NTUP_WPRIMEEN
                        D3PD output NTUP_WPRIMEEN file (can be made in
                        substeps a2d,e2d)
  --outputNTUP_IDVTXLUMIFile NTUP_IDVTXLUMI
                        D3PD output NTUP_IDVTXLUMI file (can be made in
                        substeps a2d,e2d)
  --outputNTUP_IDVTXFile NTUP_IDVTX
                        D3PD output NTUP_IDVTX file (can be made in substeps
                        a2d,e2d)
  --outputNTUP_CLUSTERCORRECTIONFile NTUP_CLUSTERCORRECTION
                        D3PD output NTUP_CLUSTERCORRECTION file (can be made
                        in substeps a2d,e2d)
  --outputNTUP_EGAMMAFile NTUP_EGAMMA
                        D3PD output NTUP_EGAMMA file (can be made in substeps
                        a2d,e2d)
  --outputNTUP_TRIGBJETFile NTUP_TRIGBJET
                        D3PD output NTUP_TRIGBJET file (can be made in
                        substeps a2d,e2d)

Additional DPDs:
  Extra DPD file types

  --outputNTUP_SCTFile NTUP_SCT
                        DPD output NTUP_SCT file
  --outputNTUP_MUFASTFile NTUP_MUFAST
                        DPD output NTUP_MUFAST file
  --outputNTUP_MUONCALIBFile NTUP_MUONCALIB
                        DPD output NTUP_MUONCALIB file
  --outputNTUP_TRKVALIDFile NTUP_TRKVALID
                        DPD output NTUP_TRKVALID file
  --outputNTUP_FASTMONFile NTUP_FASTMON
                        DPD output NTUP_FASTMON file
  --outputNTUP_LARNOISEFile NTUP_LARNOISE
                        DPD output NTUP_LARNOISE file
  --outputNTUP_WZFile NTUP_WZ
                        DPD output NTUP_WZ file
  --outputNTUP_TRTFile NTUP_TRT
                        DPD output NTUP_TRT file
  --outputNTUP_MCPFile NTUP_MCP
                        DPD output NTUP_MCP file
  --outputNTUP_HECNOISEFile NTUP_HECNOISE
                        DPD output NTUP_HECNOISE file
  --outputNTUP_ENHBIASFile NTUP_ENHBIAS
                        DPD output NTUP_ENHBIAS file
  --outputNTUP_TRUTHFile NTUP_TRUTH
                        DPD output NTUP_TRUTH file
  --outputNTUP_SUSYTRUTHFile NTUP_SUSYTRUTH
                        DPD output NTUP_SUSYTRUTH file
  --outputNTUP_HIGHMULTFile NTUP_HIGHMULT
                        DPD output NTUP_HIGHMULT file
  --outputNTUP_PROMPTPHOTFile NTUP_PROMPTPHOT
                        DPD output NTUP_PROMPTPHOT file
  --outputDESDM_BEAMSPOTFile DESDM_BEAMSPOT
                        DPD output DESDM_BEAMSPOT file
  --outputDAOD_HSG2File DAOD_HSG2
                        DPD output DAOD_HSG2 file

Reduction:
  Reduced Filetype Options

  --inputNTUP_COMMONFile INPUTNTUP_COMMONFILE [INPUTNTUP_COMMONFILE ...]
                        NTUP common input file
  --outputDNTUPFile OUTPUTDNTUPFILE
                        Reduced NTUP output filename base
  --outputDAODFile OUTPUTDAODFILE
                        Output reduced AOD filename base
  --reductionConf REDUCTIONCONF [REDUCTIONCONF ...]
                        Configuration of reduced stream outputs

Digi:
  Digitization specific options

  --inputHITSFile INPUTHITSFILE [INPUTHITSFILE ...], --inputHitsFile INPUTHITSFILE [INPUTHITSFILE ...]
                        Input HITS file
  --outputRDOFile OUTPUTRDOFILE [OUTPUTRDOFILE ...]
                        Output RDO file
  --outputRDO_FILTFile OUTPUTRDO_FILTFILE [OUTPUTRDO_FILTFILE ...]
                        Output Filtered RDO file
  --digiSeedOffset1 DIGISEEDOFFSET1
                        Offset for first random seed
  --digiSeedOffset2 DIGISEEDOFFSET2
                        Offset for second random seed
  --digiRndmSvc DIGIRNDMSVC
                        Random Number Service to use.
  --digiSteeringConf DIGISTEERINGCONF
                        Required configuration fod the digitization job
  --samplingFractionDbTag SAMPLINGFRACTIONDBTAG
                        This argument can be used to override the PhysicsList
                        retrieved from the Simulation metadata. This
                        information is used in the LAr sampling fraction data
                        base tag used by LArfSamplG4Phys.
  --doAllNoise DOALLNOISE
                        Overall control of noise simulation during
                        digitization - useful for overlay jobs, will set
                        doCaloNoise, doMuonNoise, doInDetNoise
                        digitizationFlags.
  --AddCaloDigi ADDCALODIGI
                        Save Calo Digits too, not just RawChannels.

ForwardDetector:
  Forward Detector Options

  --LucidOn LUCIDON     Switch on lucid simulation/digitization.
  --AFPOn AFPON         Switch on AFP simulation/digitization.
  --ALFAOn ALFAON       Switch on ALFA simulation/digitization.
  --ZDCOn ZDCON         Switch on ZDC simulation/digitization.
  --FwdRegionOn FWDREGIONON
                        Switch on FwdRegion simulation/digitization.

PileUp:
  Pile-Up Options

  --testPileUpConfig TESTPILEUPCONFIG
                        Calculates the number of background events that will
                        be require for a given pile-up configuration.
  --inputLowPtMinbiasHitsFile INPUTLOWPTMINBIASHITSFILE [INPUTLOWPTMINBIASHITSFILE ...], --LowPtMinbiasHitsFile INPUTLOWPTMINBIASHITSFILE [INPUTLOWPTMINBIASHITSFILE ...]
                        Input HITS file for low pT minimum bias pile-up sub-
                        events
  --inputHighPtMinbiasHitsFile INPUTHIGHPTMINBIASHITSFILE [INPUTHIGHPTMINBIASHITSFILE ...], --HighPtMinbiasHitsFile INPUTHIGHPTMINBIASHITSFILE [INPUTHIGHPTMINBIASHITSFILE ...]
                        Input HITS file for high pT minimum bias pile-up sub-
                        events
  --inputCavernHitsFile INPUTCAVERNHITSFILE [INPUTCAVERNHITSFILE ...], --cavernHitsFile INPUTCAVERNHITSFILE [INPUTCAVERNHITSFILE ...]
                        Input HITS file for cavern background sub-events
  --inputBeamHaloHitsFile INPUTBEAMHALOHITSFILE [INPUTBEAMHALOHITSFILE ...], --beamHaloHitsFile INPUTBEAMHALOHITSFILE [INPUTBEAMHALOHITSFILE ...]
                        Input HITS file for beam halo sub-events
  --inputBeamGasHitsFile INPUTBEAMGASHITSFILE [INPUTBEAMGASHITSFILE ...], --beamGasHitsFile INPUTBEAMGASHITSFILE [INPUTBEAMGASHITSFILE ...]
                        Input HITS file for beam gas sub-events
  --numberOfLowPtMinBias NUMBEROFLOWPTMINBIAS
                        Sets the intial number low pt minbias events to add on
                        average per bunch crossing. Overrides any values set
                        in joboproperties by preIncludes or preExecs. May
                        later be overridden during the job by run-dependent MC
                        code.
  --numberOfHighPtMinBias NUMBEROFHIGHPTMINBIAS
                        Sets the intial number high pt minbias events to add
                        on average per bunch crossing. Overrides any values
                        set in joboproperties by preIncludes or preExecs. May
                        later be overridden during the job by run-dependent MC
                        code.
  --numberOfBeamHalo NUMBEROFBEAMHALO
                        Sets the intial number beam halo events to add on
                        average per bunch crossing. Overrides any values set
                        in joboproperties by preIncludes or preExecs. May
                        later be overridden during the job by run-dependent MC
                        code.
  --numberOfBeamGas NUMBEROFBEAMGAS
                        Sets the intial number beam gas events to add on
                        average per bunch crossing. Overrides any values set
                        in joboproperties by preIncludes or preExecs. May
                        later be overridden during the job by run-dependent MC
                        code.
  --numberOfCavernBkg NUMBEROFCAVERNBKG
                        Sets the intial number cavern background events to add
                        on average per bunch crossing. Overrides any values
                        set in joboproperties by preIncludes or preExecs. May
                        later be overridden during the job by run-dependent MC
                        code. NB this value is an integer!
  --bunchSpacing BUNCHSPACING
                        Overrides any values of digitizationFlags.bunchSpacing
                        by preIncludes or preExecs. When using bunch structure
                        is being usedthis sets the time between successive
                        elements in the bunch structure pattern. If not using
                        bunch-structure, this can be used to run pile-up with
                        a fixed X ns spacing between filled bunch-crossings.
  --pileupInitialBunch PILEUPINITIALBUNCH
                        Initial (relative) bunch crossing to use pileup -
                        default -32
  --pileupFinalBunch PILEUPFINALBUNCH
                        Initial (relative) bunch crossing to use pileup -
                        default 32

SimDigi:
  Common Simulation Options

  --DataRunNumber DATARUNNUMBER
                        Override existing run number with this value -
                        deprecated?
  --jobNumber JOBNUMBER
                        The number of this job in the current
                        RunDependentSimulation task.

Validation Files:
  Physics validation file options

  --outputNTUP_PHYSVALFile OUTPUTNTUP_PHYSVALFILE
                        Output physics validation file

Validation Args:
  Physics validation options

  --validationFlags VALIDATIONFLAGS [VALIDATIONFLAGS ...]
                        Physics validation histogram switches
```

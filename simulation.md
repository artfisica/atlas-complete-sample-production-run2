# Simulation

GitBook allows you to organize your book into chapters, each chapter is stored in a separate file like this one.

```bash
pathena \
  --noBuild \
  --trf \
    "Sim_tf.py \
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
  --inDS user.<grid_user_name>.mc15_13TeV.305323.MGPy8EG_N30LO_A14N23LO_DM_BBscalar_p20_c1_jpt100.EVNT.v1_EXT0 \
  --outDS user.<grid_user_name>.mc15_13TeV.305323.MGPy8EG_N30LO_A14N23LO_DM_BBscalar_p20_c1_jpt100.SIM.v2 \
  --skipScout \
  --nFilesPerJob=1 \
  --destSE INFN-NAPOLI-ATLAS_LOCALGROUPDISK
```

## Help

```bash
usage: Sim_tf.py [-h] [--verbose]
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
                 [--DataRunNumber DATARUNNUMBER] [--jobNumber JOBNUMBER]
                 [--LucidOn LUCIDON] [--AFPOn AFPON] [--ALFAOn ALFAON]
                 [--ZDCOn ZDCON] [--FwdRegionOn FWDREGIONON]
                 [--inputEVNTFile INPUTEVNTFILE [INPUTEVNTFILE ...]]
                 [--outputHITSFile OUTPUTHITSFILE [OUTPUTHITSFILE ...]]
                 [--firstEvent FIRSTEVENT] [--physicsList PHYSICSLIST]
                 [--useISF USEISF]
                 [--randomSeed substep:seed [substep:seed ...]]
                 [--enableLooperKiller substep:LooperKiller [substep:LooperKiller ...]]
                 [--CosmicFilterVolume COSMICFILTERVOLUME]
                 [--CosmicFilterVolume2 COSMICFILTERVOLUME2]
                 [--CosmicPtSlice COSMICPTSLICE]
                 [--inputEVNT_COSMICSFile INPUTEVNT_COSMICSFILE [INPUTEVNT_COSMICSFILE ...]]
                 [--outputEVNT_COSMICSTRFile OUTPUTEVNT_COSMICSTRFILE [OUTPUTEVNT_COSMICSTRFILE ...]]
                 [--inputEVNT_CAVERNFile INPUTEVNT_CAVERNFILE [INPUTEVNT_CAVERNFILE ...]]
                 [--outputEVNT_CAVERNTRFile OUTPUTEVNT_CAVERNTRFILE [OUTPUTEVNT_CAVERNTRFILE ...]]
                 [--simulator CONFIGNAME] [--truthStrategy CONFIGNAME]

Transform Sim_tf. ATLAS Simulation transform. Inputs must be EVNT else a
single particle Generator job options must be specified. Outputs must be HITS
or TrackRecords.

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

SimDigi:
  Common Simulation Options

  --DataRunNumber DATARUNNUMBER
                        Override existing run number with this value -
                        deprecated?
  --jobNumber JOBNUMBER
                        The number of this job in the current
                        RunDependentSimulation task.

ForwardDetector:
  Forward Detector Options

  --LucidOn LUCIDON     Switch on lucid simulation/digitization.
  --AFPOn AFPON         Switch on AFP simulation/digitization.
  --ALFAOn ALFAON       Switch on ALFA simulation/digitization.
  --ZDCOn ZDCON         Switch on ZDC simulation/digitization.
  --FwdRegionOn FWDREGIONON
                        Switch on FwdRegion simulation/digitization.

CommonSim:
  Common Simulation Options

  --inputEVNTFile INPUTEVNTFILE [INPUTEVNTFILE ...], --inputEvgenFile INPUTEVNTFILE [INPUTEVNTFILE ...]
                        Input evgen file
  --outputHITSFile OUTPUTHITSFILE [OUTPUTHITSFILE ...], --outputHitsFile OUTPUTHITSFILE [OUTPUTHITSFILE ...]
                        Output HITS file
  --firstEvent FIRSTEVENT
                        The event number to use for the first Event
  --physicsList PHYSICSLIST
                        Physics List to be used within Geant4
  --useISF USEISF       Use ISF (only will only work from 17.6.0 onwards)
  --randomSeed substep:seed [substep:seed ...]
                        Random seed offset
  --enableLooperKiller substep:LooperKiller [substep:LooperKiller ...]
                        Should the LooperKiller be used

Cosmics:
  Cosmic Ray Simulation Options

  --CosmicFilterVolume COSMICFILTERVOLUME
                        Main Cosmic Filter Volume - tracks have to pass
                        through this volume for the event to be written out.
  --CosmicFilterVolume2 COSMICFILTERVOLUME2
                        Secondary Cosmic Filter Volume (Optional) - if
                        specified tracks also have to pass through this volume
                        for the event to be written out.
  --CosmicPtSlice COSMICPTSLICE
                        Cosmic Pt Slice

TrackRecords:
  TrackRecord related options

  --inputEVNT_COSMICSFile INPUTEVNT_COSMICSFILE [INPUTEVNT_COSMICSFILE ...]
                        Input Track Record file - sometimes used in Cosmic ray
                        simulation jobs.
  --outputEVNT_COSMICSTRFile OUTPUTEVNT_COSMICSTRFILE [OUTPUTEVNT_COSMICSTRFILE ...]
                        Output Track Record file - sometimes used in Cosmic
                        ray simulation jobs.
  --inputEVNT_CAVERNFile INPUTEVNT_CAVERNFILE [INPUTEVNT_CAVERNFILE ...]
                        Input Track Record file - sometimes used in Cavern
                        Background simulation jobs.
  --outputEVNT_CAVERNTRFile OUTPUTEVNT_CAVERNTRFILE [OUTPUTEVNT_CAVERNTRFILE ...]
                        Output Track Record file - sometimes used in Cavern
                        Background simulation jobs.

Sim_tf:
  Sim_tf specific options

  --simulator CONFIGNAME
                        Specify a named configuration. E.g. MC12G4, ATLFASTII
                        ATLFASTIIF
  --truthStrategy CONFIGNAME
                        Specify the named group of Truth strategies that the
                        ISF should use. E.g. MC12, MC15, Validation
```

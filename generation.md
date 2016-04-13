# Generation

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


# Help

```bash
usage: Generate_tf.py [-h] [--verbose]
                      [--loglevel {INFO,CRITICAL,VERBOSE,WARNING,ERROR,DEBUG,FATAL}]
                      [--argdict FILE] [--argJSON FILE] [--dumpargs]
                      [--showGraph] [--showPath] [--showSteps]
                      [--dumpPickle FILE] [--dumpJSON FILE] [--orphanKiller]
                      [--reportName REPORTNAME] [--reportType TYPE [TYPE ...]]
                      [--execOnly]
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
                      [--runNumber RUNNUMBER] [--ecmEnergy ECMENERGY]
                      [--firstEvent FIRSTEVENT]
                      [--randomSeed RANDOMSEED [RANDOMSEED ...]]
                      [--printEvts PRINTEVTS]
                      [--jobConfig JOBCONFIG [JOBCONFIG ...]]
                      [--inputGeneratorFile INPUTGENERATORFILE]
                      [--inputGenConfFile INPUTGENCONFFILE]
                      [--inputEVNTFile INPUTEVNTFILE]
                      [--inputEVNT_PreFile INPUTEVNT_PREFILE]
                      [--evgenJobOpts EVGENJOBOPTS]
                      [--outputEVNTFile OUTPUTEVNTFILE]
                      [--outputEVNT_PreFile OUTPUTEVNT_PREFILE]
                      [--outputNTUP_TRUTHFile OUTPUTNTUP_TRUTHFILE]
                      [--outputYODAFile OUTPUTYODAFILE]
                      [--rivetAnas RIVETANAS] [--outputTXTFile OUTPUTTXTFILE]

Transform Generate_tf.

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
                        substep is "all")
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

Evgen:
  Event generator options

  --runNumber RUNNUMBER, --RunNumber RUNNUMBER
                        Manual run number setting
  --ecmEnergy ECMENERGY, --EcmEnergy ECMENERGY
                        centre-of-mass energy parameter in GeV
  --firstEvent FIRSTEVENT, --FirstEvent FIRSTEVENT
                        the number of the first event in the output data file
  --randomSeed RANDOMSEED [RANDOMSEED ...], --RandomSeed RANDOMSEED [RANDOMSEED ...], --seed RANDOMSEED [RANDOMSEED ...]
                        a seed for the MC generator random number engines
  --printEvts PRINTEVTS
                        number of full event dumps to print out for debugging
  --jobConfig JOBCONFIG [JOBCONFIG ...], --JobConfig JOBCONFIG [JOBCONFIG ...], --jo JOBCONFIG [JOBCONFIG ...]
                        a comma-separated list of job configuration script
                        files
  --inputGeneratorFile INPUTGENERATORFILE, --inputGenEventFile INPUTGENERATORFILE, --inputGenFile INPUTGENERATORFILE, --InputGeneratorFile INPUTGENERATORFILE
                        optional parton-level events file to be processed
  --inputGenConfFile INPUTGENCONFFILE, --InputGenConfFile INPUTGENCONFFILE
                        optional generator configuration file
  --inputEVNTFile INPUTEVNTFILE
                        input EVNT file (for use with e.g. Rivet)
  --inputEVNT_PreFile INPUTEVNT_PREFILE
                        input evgen file for processing with afterburner, e.g.
                        EvtGen
  --evgenJobOpts EVGENJOBOPTS, --EvgenJobOpts EVGENJOBOPTS
                        download and install the EvgenJobOpts tarball with the
                        given name
  --outputEVNTFile OUTPUTEVNTFILE, --OutputEVNTFile OUTPUTEVNTFILE
                        POOL file into which generated events will be written
  --outputEVNT_PreFile OUTPUTEVNT_PREFILE, --OutputEVNT_PreFile OUTPUTEVNT_PREFILE
                        POOL file into which pre-afterburner generated events
                        will be written
  --outputNTUP_TRUTHFile OUTPUTNTUP_TRUTHFILE
                        Output NTUP_TRUTH file
  --outputYODAFile OUTPUTYODAFILE
                        Name of YODA file for Rivet histo output
  --rivetAnas RIVETANAS
                        a comma-separated list of Rivet analyses to run on the
                        resulting events
  --outputTXTFile OUTPUTTXTFILE
                        optional output TXT file for LHEF events, default is
                        None
```

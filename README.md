# HITracking_Run3_DNNstudy

Step1: CMSSW Version: CMSSW_12_5_0_pre5

Step2: cd CMSSW_12_5_0_pre5/src/

Step3: Cloned Configuration folder via git cms-addpkg Configuration/Eras/python/

Step4: cmsenv & scram b -j12

Step5: Inside src-> make 3 directories one inside another "dir1, dir2, cfg"

Step6: Inside cfg-> step4_RAW2DIGI_L1Reco_RECO_PAT.py

Step7: L8 in Configuration/Eras/python/Era_Run3_pp_on_PbPb_cff.py is :

Run3_pp_on_PbPb = cms.ModifierChain(Run3.copyAndExclude([trackdnn, trackdnn_CKF]), pp_on_AA, pp_on_PbPb_run3) 

Inside cfg-> Do voms & cmsRun step4_RAW2DIGI_L1Reco_RECO_PAT.py with above default version

Step8: Do cmsRun step4_RAW2DIGI_L1Reco_RECO_PAT.py with removing "trackdnn" from Configuration/Eras/python/Era_Run3_pp_on_PbPb_cff.py

Run3_pp_on_PbPb = cms.ModifierChain(Run3.copyAndExclude([trackdnn_CKF]), pp_on_AA, pp_on_PbPb_run3)

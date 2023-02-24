# HITracking_Run3_DNNstudy

Step1: CMSSW Version: CMSSW_12_5_0

Step2: cd CMSSW_12_5_0_pre5/src/

Step3: git cms-merge-topic mandrenguyen:trackDNN_HI_reorder

Step4: cmsenv & scram b -j12

Step5: Inside src-> make 3 directories one inside another "dir1, dir2, cfg"

Step6: Inside cfg-> step4_RAW2DIGI_L1Reco_RECO_PAT.py 

The input file & dataset used in step4_RAW2DIGI_L1Reco_RECO_PAT.py is 

file: /store/user/subehera/MB_Hydjet_Run3_GENSIM/MB_Hydjet_Run3_DIGIRAW_approxSiStripClusters/220910_091752/0000/step3_apprximateCluster_1.root 

file link: https://cmsweb.cern.ch/das/request?input=file%3D%2Fstore%2Fuser%2Fsubehera%2FMB_Hydjet_Run3_GENSIM%2FMB_Hydjet_Run3_DIGIRAW_approxSiStripClusters%2F220910_091752%2F0000%2Fstep3_apprximateCluster_1.root&instance=prod/phys03

dataset: /MB_Hydjet_Run3_GENSIM/subehera-MB_Hydjet_Run3_DIGIRAW_approxSiStripClusters-af36c27a1c89fce664821ae2610b6bbb/USER

dataset link: https://cmsweb.cern.ch/das/request?view=list&limit=50&instance=prod%2Fphys03&input=dataset%3D%2FMB_Hydjet_Run3_GENSIM%2Fsubehera-MB_Hydjet_Run3_DIGIRAW_approxSiStripClusters-af36c27a1c89fce664821ae2610b6bbb%2FUSER

Step7: L8 in Configuration/Eras/python/Era_Run3_pp_on_PbPb_cff.py is :

Run3_pp_on_PbPb = cms.ModifierChain(Run3.copyAndExclude([trackdnn, trackdnn_CKF]), pp_on_AA, pp_on_PbPb_run3) 

Inside cfg-> Do voms & cmsRun step4_RAW2DIGI_L1Reco_RECO_PAT.py with above default version

Step8: Do cmsRun step4_RAW2DIGI_L1Reco_RECO_PAT.py with removing "trackdnn" from Configuration/Eras/python/Era_Run3_pp_on_PbPb_cff.py

Run3_pp_on_PbPb = cms.ModifierChain(Run3.copyAndExclude([trackdnn_CKF]), pp_on_AA, pp_on_PbPb_run3)


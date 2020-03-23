# ECAL_Geometry_Validation
Code and instructions to validate the ECAL geometry migration to DD4HEP


To migrate the current ECAL Reco Geometry to DD4HEP the following PRs have been made to CMSSW:
29013, 29190 and 29528[Pending review].


In order to validate the ECAL Geometry migration to DD4HEP we plan to do the following :-

1) To explicitly print out the detector elements in the old and new Geometry.

2) A SIM and Reco level comparison from ele particle gun generations, ideally for all the crystals.
    --> This setup can also be used later to validate the new GEANT4 version this time with both ele and pho particle guns.

The following instructions are for (2) with the current geometry:

* The CMSSW release : CMSSW_11_1_0_pre4

* Code to generate electron events : Generate_Prompt_Electron.py
        --> Needs to be customized around lines 98-112 to choose where to shoot the electrons.

        --> Its best to write a shell script to generate a fixed number of events shooting at fixed Etas with a fixed Pt so as to be
            able to compare event by event later with the migrated geometry.

* Then we would need a upstream code to analyze the produced SimHits and RecHits.


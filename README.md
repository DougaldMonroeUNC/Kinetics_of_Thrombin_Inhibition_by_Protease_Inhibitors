# Kinetics_of_Thrombin_Inhibition_by_Protease_Inhibitors
Repository for the code used in the Blood VTH paper titled The Kinetics and Interplay of Thrombin Inhibition by Four Plasma Protease Inhibitors.

This repository has the code for studies on thrombin inhibition found at: 
DOI: https://doi.org/10.1016/j.bvth.2025.100088

Allen Ma, Dougald M Monroe, Maureane Hoffman
The Kinetics and Interplay of Thrombin Inhibition by Four Plasma Protease Inhibitors. 
Blood: Vessels, Thrombosis & Hemostasis. 2025: in press

The premise of the paper is that multiple inhibitors including antithrombin, heparin cofactor II, alpha-2-macroglobulin, and alpha-1-proteinase inhibitor contribute to thrombin inhibition in plasma. Inhibition rate constants were measured and used as the basis for an ODE model of the inhibition with varied concentrations of antithrombin and fixed concentrations of the other inhibitors. 

The code for that part of the work was written in Julia in the Jupyter notebook **ThrombinInhibitionODEs.ipynb**

The html file of the same name has the output we observed when running the code.

The models showed that as antithrombin in decreased, the rate of thrombin inhibition is decreased even in the presence of other thrombin inhibitors.

As part of the review process, we were ask to look at how these inhibitors might act in a model of thrombin generation in hemophilia. For that part of the work, we used an existing model from of the really brilliant work in:

Owen MJ, Wright JR, Tuddenham EGD, King JR, Goodall AH, Dunster JL. Mathematical models of coagulation-are we there yet? J Thromb Haemost. 2024;22(6):1689-1703. doi:10.1016/j.jtha.2024.03.009

Their original code is found at:
https://github.com/mjowen/MathematicalModelsOfCoagulation-AreWeThereYet

We used the hockin.py model and modified the code to include rates for inhibitors other than antithrombin (which was already included in hockin.py). Only thrombin inhibition was considered. 

The modified hockin.py code is found in **hockin_modified.py**. 

A summary of the changes is in the text file HockinModifiedTextOfChanges.txt. 

A Jupyter wrapper to run the hockin_modified.py code is found in **ThrombinGenerationWrapper.ipynb**.

The html file of the same name has the output we observed when running the code.

The models showed that as antithrombin in decreased, the decreased rate of thrombin inhibition result in an increased thrombin peak and area under the thrombin curve.

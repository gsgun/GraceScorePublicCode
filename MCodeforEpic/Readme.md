M Code Instructions

1) In Classic, Go to Doc Flowsshet Builder. Create Flowsheet Template (FLT) for GRACE Score and Flowsheet Group (G) for GRACE Score. For Flowsheet Group/R, row type = 2 and context = 1. For Flowsheet Template, Add Grace (G) under 1. 
2) In Text, Duplicate a Navigator Configuration VCN that will be linked to the FLT and name it GRACE. Select GRACE VCN, add FLT
3) In Classic, Go to Navigator Template and Search/Create Template, Add Section/Topic, Under Advanced, Change Default Configuration to VCN Grace

4) In Classic, Go to Doc Flowsheet Builder, Create Group/Row, 8 Rows will be created which are the variables. 4 are for the scores and interpertation.
   Create Trigger Row first which should be the last qualitative question (have to answer all the questions to get the score)
   8 - Killip Class Row Type 1 Value Type 8 Context 1
       Display - Show Values on Button Using -2 Value Only, Check Display all list choices in nvagiator
       Custom List - Check Size button width to each choice
       Custom List Values - Value (No CHF, Rales and\or JVD, Pulmonary Edema, Cardiogenic Shock)
                          - Abbreviation and Internal ID 1,2,3,4
   
   1 - Age Row type 3 Value Type 1 Context over-time
       Custom Formula: M:{Trigger Row},x=$$zCalcAge^%Zefnlii(+$h,$$getn^elibEAnLIB(""EPT"",patID,1,""100;1""))
   2 - SBP Row type 3 Value Type 1 Context over-time
       Custom Formula: M:{Trigger Row},x=$$getLastFloVal^JULIB7(inpID,"""",instant,5)
   3- Heart Rate type 3 Value Type 1 Context over-time
       M:{trigger row},x=$$getLastFloVal^JULIB7(inpID,"""",instant,8)

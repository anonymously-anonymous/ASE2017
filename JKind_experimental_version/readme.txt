To perform experiments, follow this instruction:

1- install Z3 solver, and set the $PATH variable for it
2- install JAVA 1.8
3- put jkind-api.jar along with the other two jar files in the same directory

-------------------------------  IVC_UC, IVC_UCBF, All_IVCs --------------------------
For each %FILE%:= file in the benchmarks,
Run jkind_ucbf.jar as follows:

1) for IVC_UC and All_IVCs: 

$JAVA_HOME/java -jar jkind_ucbf.jar -jkind -all_ivcs -all_assigned -solver z3 -xml %FILE%



2) after getting results from the first step, a file with "%FILE%.lus_uc.xml" will be generated, which we call %UCXML% . Now for IVC_UCBF:

$JAVA_HOME/java -jar jkind_ucbf.jar -jsupport -use_unsat_core %UCXML%  -solver z3 %FILE%

----------------------------- IVC_MUST ------------------------------------
For each %FILE%:= file in the benchmarks,
Run jkind_must.jar as follows:

3) after getting results from the first step, a file with "%FILE%.lus_uc.xml" will be generated, which we call %UCXML% . Now for IVC_MUST:

$JAVA_HOME/java -jar  jkind_must.jar -jsupport -use_unsat_core %UCXML%  -solver z3 %FILE%

-------------------------------------------------------------
Note that the ouput of each algorithm will be stored in a seperate XML file
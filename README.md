# Profiler
Uses Uniface profiler information and graphically display it allowing the user to view:
- Component/Trigger
  - Elapsed Time
  - DBMS I/O
  - Network Time
  - Idle

## Setup Instructions

1. Put the downloaded UAR somewhere and add a reference to the start of the resources section of your development asn file. 

   > [RESOURCES]
   > ..\profiler_release.uar

2. Create a uniface.exe shortcut that starts the shell 'profiler' e.g: 

   > D:\Uniface9602\common\bin\uniface.exe "/adm=D:\Uniface9602\uniface\adm" /asn="D:\Profiler96\asn\prof.asn" profiler 

3. Put the dll somewhere (e.g the working dir) and add an ASN reference

   > [USER_3GL]
   > uprofile.dll

4. Add the profiler data path and map its tables

    > [PATHS]
    > $PROF_DATA SLE:C:\ProfileData\u9profiledata.db
    >
    > [ENTITIES]
    > *.profile $PROF_DATA:*.*

5. Install vcredist_x86.exe if not already on your machine 

6. To generate a license, run the ‘profiler_smartID.exe’. This will generate a unique identifier for your machine. Email this ID to uniface.sme@uniface.com, putting the file returned into your working directory.

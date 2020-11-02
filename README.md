# utl-keep-only-the-non-missing-values-in-normalized-and-non-normalized-data-structures
Keep only the non-missing values in normalized and non normalized data structures
    Keep only the non-missing values in normalized and non normalized data structures;                                                           
                                                                                                                                                 
       Two Solutions                                                                                                                             
           a. Long Form                                                                                                                          
           b. Fat Form                                                                                                                           
                                                                                                                                                 
    github                                                                                                                                       
    https://cutt.ly/wgPRWkD                                                                                                                      
    https://github.com/rogerjdeangelis/utl-keep-only-the-non-missing-values-in-normalized-and-non-normalized-data-structures                     
                                                                                                                                                 
    SAS Forum                                                                                                                                    
    https://cutt.ly/hgPnmx5                                                                                                                      
    https://communities.sas.com/t5/SAS-Programming/how-to-get-the-not-missing-of-variables/m-p/695842                                            
                                                                                                                                                 
    *                                                                                                                                            
    #####  #   #  ####   #   #  #####                                                                                                            
      #    ##  #  #   #  #   #    #                                                                                                              
      #    # # #  #   #  #   #    #                                                                                                              
      #    #  ##  ####   #   #    #                                                                                                              
      #    #   #  #      #   #    #                                                                                                              
      #    #   #  #      #   #    #                                                                                                              
    #####  #   #  #       ###     #                                                                                                              
                                                                                                                                                 
    #! INPUT ;                                                                                                                                   
                                                                                                                                                 
    data have;                                                                                                                                   
      input                                                                                                                                      
        SUBJECT SODIUM_NLOW_VA SODIUM_NHIGH_VA POTASSIU_NLOW_VA POTASSIU_NHIGH_VA                                                                
        CARBDIOX_NHIGH_VA CHLORIDE_NLOW_VA CHLORIDE_NHIGH_VA CARBDIOX_NLOW_VA;                                                                   
    cards4;                                                                                                                                      
    1330 50 30 20 18 . . . .                                                                                                                     
    1330 50 30 20 15 . . . .                                                                                                                     
    1330 . . 80 63 . . . .                                                                                                                       
    1330 . . 80 63 . . . .                                                                                                                       
    1330 . . 53 23 . . . .                                                                                                                       
    1233 . . 53 23 . . . .                                                                                                                       
    ;;;;                                                                                                                                         
    run;quit;                                                                                                                                    
                                                                                                                                                 
    WORK.HAVE total obs=6                                                                                                                        
                                                                                                                                                 
                SODIUM_     SODIUM_    POTASSIU_    POTASSIU_    CARBDIOX_    CHLORIDE_    CHLORIDE_    CARBDIOX_                                
     SUBJECT    NLOW_VA    NHIGH_VA     NLOW_VA      NHIGH_VA     NHIGH_VA     NLOW_VA      NHIGH_VA     NLOW_VA                                 
                                                                                                                                                 
       1330        50         30           20           18           .            .            .            .                                    
       1330        50         30           20           15           .            .            .            .                                    
       1330         .          .           80           63           .            .            .            .                                    
       1330         .          .           80           63           .            .            .            .                                    
       1330         .          .           53           23           .            .            .            .                                    
       1233         .          .           53           23           .            .            .            .                                    
                                                                                                                                                 
    *                                                                                                                                            
     ###   #   #  #####  ####   #   #  #####                                                                                                     
    #   #  #   #    #    #   #  #   #    #                                                                                                       
    #   #  #   #    #    #   #  #   #    #                                                                                                       
    #   #  #   #    #    ####   #   #    #                                                                                                       
    #   #  #   #    #    #      #   #    #                                                                                                       
    #   #  #   #    #    #      #   #    #                                                                                                       
     ###    ###     #    #       ###     #                                                                                                       
    *                                                                                                                                            
    #       ###   #   #   ###                                                                                                                    
    #      #   #  ##  #  #   #                                                                                                                   
    #      #   #  # # #  #                                                                                                                       
    #      #   #  #  ##  # ###                                                                                                                   
    #      #   #  #   #  #   #                                                                                                                   
    #      #   #  #   #  #   #                                                                                                                   
    #####   ###   #   #   ###                                                                                                                    
                                                                                                                                                 
    #! LONG ;                                                                                                                                    
                                                                                                                                                 
                                                                                                                                                 
    WORK.WANTNRM total obs=16                                                                                                                    
                                                                                                                                                 
     SUBJECT           KEY           VAL                                                                                                         
                                                                                                                                                 
       1330     SODIUM_NLOW_VA        50                                                                                                         
       1330     SODIUM_NHIGH_VA       30                                                                                                         
       1330     POTASSIU_NLOW_VA      20                                                                                                         
       1330     POTASSIU_NHIGH_VA     18                                                                                                         
       1330     SODIUM_NLOW_VA        50                                                                                                         
       1330     SODIUM_NHIGH_VA       30                                                                                                         
       1330     POTASSIU_NLOW_VA      20                                                                                                         
       1330     POTASSIU_NHIGH_VA     15                                                                                                         
       1330     POTASSIU_NLOW_VA      80                                                                                                         
       1330     POTASSIU_NHIGH_VA     63                                                                                                         
       1330     POTASSIU_NLOW_VA      80                                                                                                         
       1330     POTASSIU_NHIGH_VA     63                                                                                                         
       1330     POTASSIU_NLOW_VA      53                                                                                                         
       1330     POTASSIU_NHIGH_VA     23                                                                                                         
       1233     POTASSIU_NLOW_VA      53                                                                                                         
       1233     POTASSIU_NHIGH_VA     23                                                                                                         
                                                                                                                                                 
    *                                                                                                                                            
    #####    #    #####                                                                                                                          
    #       # #     #                                                                                                                            
    #      #   #    #                                                                                                                            
    ####   #####    #                                                                                                                            
    #      #   #    #                                                                                                                            
    #      #   #    #                                                                                                                            
    #      #   #    #                                                                                                                            
                                                                                                                                                 
    #! FAT ;                                                                                                                                     
                                                                                                                                                 
                                                                                                                                                 
    WORK.WANTFAT total obs=6                                                                                                                     
                                                                                                                                                 
                 SODIUM_     SODIUM_    POTASSIU_    POTASSIU_                                                                                   
      SUBJECT    NLOW_VA    NHIGH_VA     NLOW_VA      NHIGH_VA                                                                                   
                                                                                                                                                 
        1330        50         30           20           18                                                                                      
        1330        50         30           20           15                                                                                      
        1330         .          .           80           63                                                                                      
        1330         .          .           80           63                                                                                      
        1330         .          .           53           23                                                                                      
        1233         .          .           53           23                                                                                      
                                                                                                                                                 
    *                                                                                                                                            
    ####   ####    ###    ###   #####   ###    ###                                                                                               
    #   #  #   #  #   #  #   #  #      #   #  #   #                                                                                              
    #   #  #   #  #   #  #      #       #      #                                                                                                 
    ####   ####   #   #  #      ####     #      #                                                                                                
    #      # #    #   #  #      #         #      #                                                                                               
    #      #  #   #   #  #   #  #      #   #  #   #                                                                                              
    #      #   #   ###    ###   #####   ###    ###                                                                                               
                                                                                                                                                 
    *                                                                                                                                            
    #       ###   #   #   ###                                                                                                                    
    #      #   #  ##  #  #   #                                                                                                                   
    #      #   #  # # #  #                                                                                                                       
    #      #   #  #  ##  # ###                                                                                                                   
    #      #   #  #   #  #   #                                                                                                                   
    #      #   #  #   #  #   #                                                                                                                   
    #####   ###   #   #   ###                                                                                                                    
                                                                                                                                                 
    #! PROCESS ;                                                                                                                                 
    proc datasets lib=work nolist;                                                                                                               
      delete wantNrm;                                                                                                                            
    run;quit;                                                                                                                                    
                                                                                                                                                 
    %utl_gather(have,key,val,subject,wantNrm(where=(val ne .)),valFormat=4.);                                                                    
                                                                                                                                                 
    *                                                                                                                                            
    #####    #    #####                                                                                                                          
    #       # #     #                                                                                                                            
    #      #   #    #                                                                                                                            
    ####   #####    #                                                                                                                            
    #      #   #    #                                                                                                                            
    #      #   #    #                                                                                                                            
    #      #   #    #                                                                                                                            
                                                                                                                                                 
    #! FAT ;                                                                                                                                     
                                                                                                                                                 
    %arraydelete(vrs);       * just in case? ;                                                                                                   
    %symdel popVar / nowarn; * just in case? ;                                                                                                   
                                                                                                                                                 
    proc datasets lib=work nolist;                                                                                                               
      delete wantMrg wantXpowantFat;                                                                                                             
    run;quit;                                                                                                                                    
                                                                                                                                                 
    * put varuable names that end with VA into sn array;                                                                                         
    %array(vrs,values=%varlist(have,prx=/VA$/i));                                                                                                
                                                                                                                                                 
    * merge non-missing values variable by variable;                                                                                             
    data wantMrg;                                                                                                                                
      merge                                                                                                                                      
        %do_over(vrs,phrase=%str(have(where=(not missing(?)) keep=subject ? )))                                                                  
      ;                                                                                                                                          
       by descending subject;                                                                                                                    
       output;                                                                                                                                   
       %do_over(vrs,phrase=%str(?=.;));                                                                                                          
    run;quit;                                                                                                                                    
                                                                                                                                                 
    * keep stack non-missing values and remover 100% missing variables;                                                                          
    data wantFat;                                                                                                                                
      if _n_=0 then do; %dosubl('                                                                                                                
           proc transpose data=wantMrg(obs=1) out=wantXpo(where=(col1 ne .));                                                                    
           run;quit;                                                                                                                             
           data _null_;                                                                                                                          
               retain popVar;                                                                                                                    
               length popVar  $96 ;                                                                                                              
               set wantXpo end=dne;                                                                                                              
               popVar=catx(" ",popVar,_name_);                                                                                                   
               put popVar=;                                                                                                                      
               call symputx("popVar",popVar);                                                                                                    
           run;quit;                                                                                                                             
          ');                                                                                                                                    
      end;                                                                                                                                       
      set wantMrg(keep=&popvar);                                                                                                                 
    run;quit;                                                                                                                                    
                                                                                                                                                 
    %arraydelete(vrs);                                                                                                                           
                                                                                                                                                 
                                                                                                                                                 

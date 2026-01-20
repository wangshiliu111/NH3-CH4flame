# SJTU Combustor Simulation - FRC Case with Fast Chemistry  Solver                   
                                                                                
 ## Overview                                                                    
 This case simulates the SJTU (Shanghai Jiao Tong University) combustor using   
 fast chemistry approach with **reactingFoam** solver in OpenFOAM. Both the     
 main inlet and pilot flame are fueled, representing a realistic dual-fuel      
 injection configuration.                                                       
                                                                                
 ## Case Configuration                                                          
                                                                                
 ### Flow Configuration                                                         
 - **Equivalence Ratio (φ)**: 0.9 (lean combustion)                             
 - **Mixture Parameter (ζ)**: 0.2                                               
 - **Fuel**: CH4/NH3/Air mixture with Okafor chemistry                            
 - **Inlet Configuration**: Dual-fuel injection (main inlet + pilot)            
                                                                                
 ### Numerical Setup                                                            
 - **Solver**: reactingFoam                                                     
 - **Turbulence Model**: RAS (Reynolds-Averaged Simulation)                                           
 - **Chemistry Model**: Laminar (fast chemistry solver)
 - fast chemistry solver: [https://github.com/yuchenzh/pureChemistryModel-of7](https://github.com/yuchenzh/pureChemistryModel-of7)                                                             
                                                                                
      
                                                                                
 ### Execution                                                                  
 ```bash                                                                        
 # Start from latest time                                                       
 reactingFoam                                                                   
                                                                                
 # Or run in parallel                                                           
 decomposePar                                                                   
 mpirun -np <ncores> reactingFoam -parallel
 ```                                                     
                                                                                
 ### Prerequisites                                                              
 - OpenFOAM 7 or compatible version                                             
 - Custom libraries: `libpureChemistryModel.so`     
                                                                                

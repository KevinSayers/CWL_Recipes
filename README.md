# CWL_Recipes
Various CWL examples I found useful 


# File[] with InitialWorkDirRequirement

If a workflow step needs multiple files to run, such as index files for tophat, one solution
is to have a step output a File[]. Using InitialWorkDirRequirement in the dependent step with the indexing for each of the files. This seems to be necessary as the items in 'listing' can not be of type File[]. This could potentially be improved with a more complete javascript expression to do each of the item in the array. 

'''
requirements:
  - class: InlineJavascriptRequirement
  - class: InitialWorkDirRequirement
    listing:
      - $(inputs.indexs[0])
      - $(inputs.indexs[1])
      - $(inputs.indexs[2])
      - $(inputs.indexs[3])
      - $(inputs.indexs[4])
      - $(inputs.indexs[5])
'''


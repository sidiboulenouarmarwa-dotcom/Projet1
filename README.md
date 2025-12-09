# Projet1
#pandas with sidi boulenouar marwa nawel master 1 B.A 10/12/2025
#Ziani Nourhan
#Zerrouki Khawla 
#Haddouche Bouchra
import pandas as pd 

# Données : Séquences ADN, Longueur, Pourcentage de GC 

data= { "Séquence": ["ATGCGTACGTA","GCTAGCTAGGCC","ATGCGCGTAAGT","TACGATCGTA","ATGAAAGGCTT","CGTACGTAGC","TTAACCGGAT"],
    "Longueur":[11,12,12,10,11,10,10], 
    "Pourcentage GC":[50,66.67,58.33,40,45.45,60,50] 
    }
# Créaction d'un DataFrame ( tableau pandas )
df=pd.DataFrame(data) 
print("*************Creation et affichage *************")

#Affichage du tableau 
print("tableau des séquences ADN :")
print(df,"\n\n")

# Opérations sur Les tableaux: 
print("************* Operations *************")

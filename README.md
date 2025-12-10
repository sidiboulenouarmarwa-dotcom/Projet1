#project1
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

# Affichage du tableau 
print("tableau des séquences ADN :")
print(df,"\n\n")

# Opérations sur Les tableaux: 
print("************* Operations *************")

# 2) Sélectionner la colonne "Longueur"
longueur = df["Longueur"]
print(longueur)

# 3) Filtrer les séquences avec un pourcentage de GC supérieur à 10%
print("*************Filtrage avec pourcentage % *************")
# Filtrer les séquences avec un pourcentage de GC supérieur à 10 
filtered_df = df[df["Pourcentage GC"]  > 10 ]
print(filtered_df,"\n\n")

# 4) Calculer la moyenne du pourcentage de GC 
print("************ Calcul de la moyenne *************")
# Calculer la moyenne du pourcentage de GC 
average_gc = df["Pourcentage GC"].mean()
print(f"Pourcentage moyen de GC : {average_gc:.3f}%")

# 5) Ajouter une nouvelle colonne  "Catégorie GC" 
print("********** Ajout de la colonne Catégorie GC **********") 
# Ajouter une nouvelle colonne "Catégorie GC"
def categorie_gc(gc): 
    if gc > 55:
       return  "Riche" 
    elif gc >= 45:
       return "Moyen" 
    else: 
       return "Faible" 

df["Catégorie GC"] = df["Pourcentage  GC"].apply(categorie_gc)

print(df) 


# 6)Ajouter une colonne donnant le nombre de 'G' dans chaque séquences
df["Nombre de G"] = df["Séquence"].str.count("G") 

print("==== Nombre de G ajoutés ====") 
print(df,"\n") 


# 7) Calculer L'écart-type du %GC et de La Longueur des séquences
print("**********Écart-type **********")

ecart_type_gc = df["Pourcentage GC"].std()
ecart_type_longueur = df["Longueur"].std()

print("Écart-type du %GC :", ecart_type_gc)
print("Écart-type de La Longueur :", ecart_type_longueur)

# 8) Sauvegarde et changement des données avec panda 
# sauvegarde Le DataFrame dans un fichier CSV
df.to_csv ("tableau_sequences.csv", index =false)


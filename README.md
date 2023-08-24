# Example_DietOverlap
````

names <- c("bluegill","perch","minnows","bullheads","insects","zooplankton")
lmb <- c(55,35,23,7,3,1)
wae <- c(23,45,2,17,7,2)
dietOverlap(lmb,wae,prey=names,type="Horn")


####now I try with my data
table_ASVs_subspecies=read.table("rbcL_gemapisr_ASV_vs_subspecies.txt", 
                                 header = T,
                                 row.names = 1,
                                 check.names = FALSE)
head(table_ASVs_subspecies)[1:2,]
dim(table_ASVs_subspecies)

dietnanus <- table_ASVs_subspecies$A_c_nanus
diethayampi <- table_ASVs_subspecies$A_c_hayampi
dietsielmanni  <- table_ASVs_subspecies$A_c_sielmanni
dietmertensi <- table_ASVs_subspecies$A_c_mertensi
dietgodzilla <- table_ASVs_subspecies$A_c_godzilla
dietinvent <- table_ASVs_subspecies$A_c_inventada_hayampi

dietOverlap(dietgodzilla,dietmertensi,dietsielmanni,diethayampi,dietnanus, type="Schoener")
dietOverlap(dietgodzilla,dietmertensi, type="Schoener")
dietOverlap(dietgodzilla,dietsielmanni, type="Schoener")
dietOverlap(dietgodzilla,diethayampi, type="Schoener")
dietOverlap(dietgodzilla,dietnanus, type="Schoener")
dietOverlap(dietmertensi,dietsielmanni, type="Schoener")
dietOverlap(dietmertensi,diethayampi, type="Schoener")
dietOverlap(dietmertensi,dietnanus, type="Schoener")
dietOverlap(dietsielmanni,diethayampi, type="Schoener")
dietOverlap(dietsielmanni,dietnanus, type="Schoener")
dietOverlap(diethayampi,dietnanus, type="Schoener")
dietOverlap(diethayampi,dietinvent, type="Schoener")

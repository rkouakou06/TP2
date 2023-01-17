"""Importation du module sys et du module os"""
import sys
import os
ADN_LIST=("A","C","G","T")
def adn_read(fastafile):
    """fonction permettant de controler les nucléotides d'un fichier fasta"""
    with open(fastafile,"r") as file:
        lines = file.readlines()
        lines_counter = 0
        header = ""
        for line in lines:
            lines_counter += 1
            if line[0] == ">":
                header = line.strip()
            else:
                line = line.strip()
                line = line.upper()
                column_counter = 0
                for char in line:
                    column_counter += 1
                    if char not in ADN_LIST:
                        print(fastafile+" : "+char+" It's not a nucl in line "+str(lines_counter)+
                        " and column "+str(column_counter)+" for sequence "+header[1:])
for arg in sys.argv[1:]:
    if os.path.exists(arg) is True:
        if arg.endswith(".fasta" or ".fa"):
            print(arg + " : This is a fasta file")
            adn_read(arg)
        else:
            print(arg + " : This is not a fasta file")
    else:
        print(arg + " : This file doesn't exist")


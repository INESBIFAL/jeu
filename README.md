# jeu

# Import de module ----------------------- #

from operator import ge
import tkinter as tk 
import random

#Constantes --------------------------------#
LARGEUR = 500
HAUTEUR = 500
CASES = 4
LARGE_CASES = LARGEUR//CASES
HAUT_CASES = HAUTEUR//CASES

#VARIABLES GLOBAL ---------------------------#



# Fonction-------------------------------------#

def init(can):
    global LARGE_CASES, HAUT_CASES
    return [can.create_rectangle ((i*LARGE_CASES), (j*HAUT_CASES), ((i+1)*LARGE_CASES), ((j+1)*HAUT_CASES), fill='black' , outline = 'white') for i in range (CASES) for j in range (CASES)]

def generer():
    t = [i for i in range(1, CASES**2)]
    random.shuffle(t)
    t.append(0)


#Main ----------------------------------------#

#------------FENETRE-------------------------#
racine = tk.Tk()
racine.title("Taquin")


#---------------Widget------------------------#

#-----Canvas----------#
canvas = tk.Canvas (racine, bg="green", width= LARGEUR, height= HAUTEUR)
canvas.grid()
tableau = init(canvas)
#---Menu---#
canvas = tk.Canvas(racine, width=LARGEUR, height=HAUTEUR)


racine.mainloop()


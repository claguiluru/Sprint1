# Sprint1 - Capítulo 7
Primeiro Sprint realizado pelo método SCRUM
import re
import sys
def telefone(text):
    tel = re.compile(r'(\(\d\d\))?( )?(\d\d\d\d-\d\d\d\d)')
    print ("Numeros encontrados: ")
    print (tel.findall(text))

def email(text):
    email = re.compile(r'[a-zA-Z0-9._]+@[a-zA-Z.]+\.[combr]{2,4}')
    print("E-maisl encontrados: ")
    print(email.findall(text))


text = input("Cole o texto aqui: ")
text.replace("\n","")
telefone(text)
email(text)

text = input("\n\nPressione qualquer tecla para fechar")

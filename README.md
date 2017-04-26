# Sprint1 - Expressões Regulares
Primeiro Sprint realizado pelo método SCRUM
def NumTelefone(texto):
        texto.replace(" ","")
        if len(texto) != 13:
            return False

        for i in range(1,2):
            if not texto[i].isdecimal():    
                return False
        if texto[0] != '(' or texto[3] !=')' or texto[8] != '-':
            return False
        for i in range (4,7):
            if not texto[i].isdecimal():
                return False
        for i in range(9,12):
            if not texto[i].isdecimal():
                return False

        return True


def Email(texto):
        counter = 0
        tam=len(texto)
        for i in range(tam):
                if texto[i] == ' ' or texto[i] == '!' or texto[i] == '?':
                    return False
                if texto[i] == ']' or texto[i] == '/' or texto[i] == ')':
                    return False
                if texto[i] == '@':
                    counter = counter + 1
        if counter != 1:
                return False
        if texto[tam-4:] != 'm.br' and texto[tam-4:] != '.com':
                return False
        return True


def Endereco(texto):
    tam = len(texto)
    if texto[0:3].lower()!= 'rua' and texto[0:2].lower()!= 'r.':
        if texto[0:7].lower()!= 'avenida' and texto[0:3] != 'av.': 
            return False
    if not texto[tam-1].isdecimal():
        return False
    return True


textos = ["(34)9912-3456", "Avenida Segismundo Pereira, 712", "Ruanita", "lucas.geramano08@hotmail.com", "http://www.moodle.ufu.br", "Rua Prata, 712"]
for i in range(0,6):
        if NumTelefone(textos[i]):
                print ("%s e um  numero de telefone" %textos[i]) 
        if Email(textos[i]):
                print ("%s e um  e-mail" %textos[i]) 
        if Endereco(textos[i]):
                print ("%s e um  endereco" %textos[i])

text = input("\n\n Pressione qualquer tecla para sair")
        


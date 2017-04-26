# Sprint1 - Capítulo 8
Primeiro Sprint realizado pelo método SCRUM
import random

capitais = {'Alabama': 'Montgomery', 'Alaska': 'Juneau', 'Arizona': 'Phoenix', 'Arkansas': 'Little Rock', 'California': 'Sacramento', 'Colorado': 'Denver', 'Connecticut': 'Hartford', 'Delaware': 'Dover', 'Florida': 'Tallahassee', 'Georgia': 'Atlanta', 'Hawaii': 'Honolulu', 'Idaho': 'Boise', 'Illinois': 'Springfield', 'Indiana': 'Indianapolis', 'Iowa': 'Des Moines', 'Kansas': 'Topeka', 'Kentucky': 'Frankfort', 'Louisiana': 'Baton Rouge', 'Maine': 'Augusta', 'Maryland': 'Annapolis', 'Massachusetts': 'Boston', 'Michigan': 'Lansing', 'Minnesota': 'Saint Paul', 'Mississippi': 'Jackson', 'Missouri': 'Jefferson City', 'Montana': 'Helena', 'Nebraska': 'Lincoln', 'Nevada': 'Carson City', 'New Hampshire': 'Concord', 'New Jersey': 'Trenton', 'New Mexico': 'Santa Fe', 'New York': 'Albany', 'North Carolina': 'Raleigh', 'North Dakota': 'Bismarck', 'Ohio': 'Columbus', 'Oklahoma': 'Oklahoma City', 'Oregon': 'Salem', 'Pennsylvania': 'Harrisburg', 'Rhode Island': 'Providence', 'South Carolina': 'Columbia', 'South Dakota': 'Pierre', 'Tennessee': 'Nashville', 'Texas': 'Austin', 'Utah': 'Salt Lake City', 'Vermont': 'Montpelier', 'Virginia': 'Richmond', 'Washington': 'Olympia', 'West Virginia': 'Charleston', 'Wisconsin': 'Madison', 'Wyoming': 'Cheyenne'}
# A variável capitais contém os nomes das capitais estadunidenses

for quizNum in range(35): 
    quizFile = open('quiz%s.txt' % (quizNum + 1), 'w')
    respostaFile = open('quiz_resposta%s.txt' % (quizNum + 1), 'w')
    estado = list(capitais.keys()) 
    random.shuffle(estado) 

    for Num in range(50):

        correta = capitais[estado[Num]]
        incorreta = list(capitais.values()) 
        del incorreta[incorreta.index(correta)] 
        incorreta = random.sample(incorreta, 3) 

        alternativas = incorreta + [correta]
        random.shuffle(alternativas) 

        quizFile.write('%s. Qual a capital de %s?\n' % (Num + 1, estado[Num]))
        for i in range(4):
            quizFile.write('    %s. %s\n' % ('ABCD'[i], alternativas[i]))
        quizFile.write('\n')

        respostaFile.write('%s. %s\n' % (Num + 1, 'ABCD'[alternativas.index(correta)]))
    quizFile.close()
    respostaFile.close()

	

# ---------- FUNÇÕES ----------



def cadastrar_disciplinas():

 disciplinas = []



 while True:

  nome = input("Digite seu nome: ").strip()

  if nome:

   break



 while True:

  qtd = int(input("Quantas disciplinas deseja cadastrar? "))

  if qtd > 0:

   break



 for i in range(qtd):

  print(f"\nDisciplina {i+1}")



  while True:

   disciplina = input("Nome da disciplina: ").strip()

   if disciplina:

    break



  while True:

   nota1 = float(input("Nota 1: "))

   if 0 <= nota1 <= 10:

    break



  while True:

   nota2 = float(input("Nota 2: "))

   if 0 <= nota2 <= 10:

    break



  while True:

   frequencia = float(input("Frequência (%): "))

   if 0 <= frequencia <= 100:

    break



  disciplinas.append({

   "nome": disciplina,

   "nota1": nota1,

   "nota2": nota2,

   "frequencia": frequencia

  })



 return nome, disciplinas





def calcular_media(n1, n2):

 return (n1 + n2) / 2





def verificar_frequencia(freq):

 return freq >= 75





def gerar_relatorio(nome, disciplinas):

 print("\n--- RESULTADO FINAL ---")



 for d in disciplinas:

  media = calcular_media(d["nota1"], d["nota2"])

  freq_ok = verificar_frequencia(d["frequencia"])



  print("\nAluno:", nome)

  print("Disciplina:", d["nome"])

  print("Média:", round(media, 2))

  print("Frequência:", d["frequencia"])



  if media >= 7 and freq_ok:

   print("Situação: Aprovado")

  elif media < 7 and freq_ok:

   print("Situação: Reprovado por nota")

  elif media >= 7 and not freq_ok:

   print("Situação: Reprovado por frequência")

  else:

   print("Situação: Reprovado por nota e frequência")





# ---------- PROGRAMA PRINCIPAL ----------



nome, disciplinas = cadastrar_disciplinas()

gerar_relatorio(nome, disciplinas)

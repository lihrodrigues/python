class Veiculo:
  def __init__(self,marca,ano):
      self.marca= marca
      self.ano= ano
  def exibir_informacoes(self):
    print("marca:",self.marca)
    print("ano:",self.ano)

class Carro(Veiculo):
  def __init__(self,marca,ano,quantidade_portas):
    super().__init__(marca,ano)
    self.quantidade_portas=quantidade_portas
  def exibir_informacoes(self):
    super().exibir_informacoes()
   

class Caminhao(Veiculo):
  def __init__(self,marca,ano,capacidade_carga):
    super().__init__(marca,ano)
    self.capacidade_carga=capacidade_carga
  def exibir_informacoes(self):
    super().exibir_informacoes()
    print("capacidade/carga:", self.capacidade_carga)

#Exmplo de uso
carro=Carro("toyota",2020,4)
caminhao=Caminhao("Volvo",2019,20)
veiculos=[carro,caminhao]
for i in veiculos:
    i.exibir_informacoes()

carro1=Carro("GM",2020,4)
carro2=Carro("VW",2018,2)
Ccarro3=Carro("fiat",2014,2)
caminhao1=Caminhao("Scania",2015,5000)
caminhao2=Caminhao("Volvo",2020,8000)
print(carro1)
print("marca:",carro1.marca,"ano:",carro1.ano,"quantidade_portas:",carro1.quantidade_portas)
print("marca:",caminhao1.marca,"ano:",caminhao1.ano,"capacidade:",caminhao1.capacidade_carga)

opcao="s"
while(opcao=="s"or opcao=="S"):
  x=int(input("É carro(1) ou caminhão (2)?"))
  marca=input("digite a marca:")
  ano=int(input("digite o ano:"))
  valido=0
  while valido==0:
    try:
      ano=int(input("digite o ano:"))
      valido=1
    except ValueError:
      print("valor errado. Digite novamente!")
  if x==1:
    portas=int(input("digite a quantidade de portas:"))
    car=Carro(marca,ano,portas)
    veiculos.append (car)
  elif x==2:
      cap=int(input("digite a capacidade de caminhão:"))
      cam=Caminhao(marca,ano,cap)
      veiculos.append(cam)
      opcao=input("quer continuar? <s/n>")
      print("\nImprimindo todos...")
      for i in range (len(veiculos)):
        veiculos[i].exibir_informacoes() 

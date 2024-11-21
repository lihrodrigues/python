class Veiculo:
    def __init__(self, placa, preco, marca, modelo):
        self.placa = placa
        self.preco = preco
        self.marca = marca
        self.modelo = modelo

    def __str__(self):
        return f"Placa: {self.placa}, Preço: R${self.preco:.2f}, Marca: {self.marca}, Modelo: {self.modelo}"


class LojaAutomoveis:
    def __init__(self):
        self.veiculos = []  # Array de objetos da classe Veiculo

    def inserir_veiculo(self, placa, preco, marca, modelo):
        novo_veiculo = Veiculo(placa, preco, marca, modelo)
        self.veiculos.append(novo_veiculo)
        print(f"Veículo com placa {placa} inserido com sucesso.")

    def remover_veiculo(self, placa):
        for veiculo in self.veiculos:
            if veiculo.placa == placa:
                self.veiculos.remove(veiculo)
                print(f"Veículo com placa {placa} removido com sucesso.")
                return
        print(f"Veículo com placa {placa} não encontrado.")

    def alterar_veiculo(self, placa, preco=None, marca=None, modelo=None):
        for veiculo in self.veiculos:
            if veiculo.placa == placa:
                if preco is not None:
                    veiculo.preco = preco
                if marca is not None:
                    veiculo.marca = marca
                if modelo is not None:
                    veiculo.modelo = modelo
                print(f"Veículo com placa {placa} atualizado com sucesso.")
                return
        print(f"Veículo com placa {placa} não encontrado.")

    def listar_veiculos(self):
        if not self.veiculos:
            print("Nenhum veículo disponível.")
        else:
            print("Lista de veículos:")
            for veiculo in self.veiculos:
                print(veiculo)


# Exemplo de uso do sistema
loja = LojaAutomoveis()

# Inserindo veículos
loja.inserir_veiculo("ABC1234", 50000, "Toyota", "Corolla")
loja.inserir_veiculo("XYZ5678", 40000, "Honda", "Civic")
loja.inserir_veiculo("LMN8910", 30000, "Ford", "Focus")

# Listando veículos
loja.listar_veiculos()

# Alterando um veículo
loja.alterar_veiculo("ABC1234", preco=52000, modelo="Corolla X")

# Removendo um veículo
loja.remover_veiculo("XYZ5678")

# Listando veículos novamente
loja.listar_veiculos()

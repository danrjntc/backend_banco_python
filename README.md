class ContaBancaria:
    def __init__(self, saldo=0):
        self.saldo = saldo

    def depositar(self, valor):
        self.saldo += valor
        print(f'Depósito de R${valor} realizado. Novo saldo: R${self.saldo}')

    def sacar(self, valor):
        if valor > self.saldo:
            print('Saldo insuficiente. Operação não realizada.')
        else:
            self.saldo -= valor
            print(f'Saque de R${valor} realizado. Novo saldo: R${self.saldo}')

    def extrato(self):
        print(f'Saldo atual: R${self.saldo}')

# Função principal
def main():
    conta = ContaBancaria()

    while True:
        print("\nOpções:")
        print("1 - Depositar")
        print("2 - Sacar")
        print("3 - Extrato")
        print("4 - Sair")

        escolha = input("Escolha uma opção (1/2/3/4): ")

        if escolha == '1':
            valor_deposito = float(input("Digite o valor a depositar: "))
            conta.depositar(valor_deposito)

        elif escolha == '2':
            valor_saque = float(input("Digite o valor a sacar: "))
            conta.sacar(valor_saque)

        elif escolha == '3':
            conta.extrato()

        elif escolha == '4':
            print("Saindo do programa. Obrigado!")
            break

        else:
            print("Opção inválida. Tente novamente.")

if __name__ == "__main__":
    main()

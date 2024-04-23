saldo = 0.0
depositos = []
saques = []

valor_deposito = float(input("Digite o valor a ser depositado (R$): "))
saldo += valor_deposito
depositos.append(valor_deposito)

LIMITE_SAQUES_DIARIOS = 3
LIMITE_SAQUE = 500.0

valor_saque = float(input("Digite o valor a ser sacado (R$): "))
if saldo >= valor_saque and len(saques) < LIMITE_SAQUES_DIARIOS and valor_saque <= LIMITE_SAQUE:
    saldo -= valor_saque
    saques.append(valor_saque)
else:
    print("Não é possível sacar esse valor. Verifique o saldo ou limite de saques.")

print("\nExtrato:")
for deposito in depositos:
    print(f"Depósito: R${deposito:.2f}")
for saque in saques:
    print(f"Saque: R${saque:.2f}")
print(f"Saldo atual: R${saldo:.2f}")

if __name__ == "__main__":
    while True:
        print("\nOpções:")
        print("1. Depósito")
        print("2. Saque")
        print("3. Extrato")
        opcao = int(input("Escolha uma opção (1/2/3): "))

        if opcao == 1:
            # Realiza depósito
            valor_deposito = float(
                input("Digite o valor a ser depositado (R$): "))
            saldo += valor_deposito
            depositos.append(valor_deposito)
        elif opcao == 2:
            # Realiza saque
            valor_saque = float(input("Digite o valor a ser sacado (R$): "))
            if saldo >= valor_saque and len(saques) < LIMITE_SAQUES_DIARIOS and valor_saque <= LIMITE_SAQUE:
                saldo -= valor_saque
                saques.append(valor_saque)
            else:
                print(
                    "Não é possível sacar esse valor. Verifique o saldo ou limite de saques.")
        elif opcao == 3:
            # Exibe extrato
            print("\nExtrato:")
            for deposito in depositos:
                print(f"Depósito: R${deposito:.2f}")
            for saque in saques:
                print(f"Saque: R${saque:.2f}")
            print(f"Saldo atual: R${saldo:.2f}")
        else:
            print("Opção inválida. Tente novamente.")



clientes = {}

while True:
    print("\n=== SISTEMA DE CRÉDITO ===")
    print("1 - Adicionar crédito")
    print("2 - Consultar saldo")
    print("3 - Listar clientes")
    print("4 - Sair")

    opcao = input("Escolha uma opção: ")

    if opcao == "1":
        nome = input("Nome do cliente: ").strip().title()
        valor = float(input("Valor a adicionar: R$ "))

        if nome in clientes:
            clientes[nome] += valor
        else:
            clientes[nome] = valor

        print(f"Crédito adicionado! Saldo de {nome}: R$ {clientes[nome]:.2f}")

    elif opcao == "2":
        nome = input("Nome do cliente: ").strip().title()

        if nome in clientes:
            print(f"Saldo de {nome}: R$ {clientes[nome]:.2f}")
        else:
            print("Cliente não encontrado.")

    elif opcao == "3":
        print("\n=== CLIENTES CADASTRADOS ===")

        if not clientes:
            print("Nenhum cliente cadastrado.")
        else:
            for nome, saldo in clientes.items():
                print(f"{nome}: R$ {saldo:.2f}")

    elif opcao == "4":
        print("Sistema encerrado.")
        break

    else:
        print("Opção inválida!")
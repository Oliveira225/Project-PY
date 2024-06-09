saldo = 0

limite = 500

extrato = ""

limite_saque = 3

numero_saque = 0

 

menu = """

|[0] Sair       |

|[1] Depositar  |

|[2] Saque      | 

|[3] Extrato    |

-----------------

Digite aqui: """

 

while True:

    opcao = input (menu)

   

    if opcao == "1":

        valor = float (input("Informe o valor do deposito: "))

      

 

        if valor > 0:

            saldo += valor

            extrato += f"Deposito : R$: {valor:.2f}\n"

        else:

            print ("Erro, valor invalido. Tente novamente!")

 

    elif opcao == "2"        :

        valor = float(input("Informe o valor do deposito: "))

 

        excedeu_saldo = valor > saldo

        excedeu_limite = valor > limite

        excedeu_saques = numero_saque >= limite_saque

 

        if excedeu_saldo:

            print("Erro! Limite de saldo insuficiente".title())

        elif excedeu_limite:

            print("Erro! Você atingiu o limite.".title())

        elif excedeu_saques:

            print("Erro! limite de Saques excedido!".title())

        elif valor > 0:
            saldo -= valor
            extrato += f"Saque R$: {valor:.2f}"
            numero_saque += 1
            
        
        else:
            print("Erro, valor informado é invalido.".title())
            1
    elif opcao == "3":
        print("\n*************Extrato*************")  
        print("Não foram realizadas movimentações" if not extrato else extrato)
        print(f"\n Saldo: R$: {saldo:.2f}")  
        print("***********************************")
    elif opcao == "0":
        break
    else:
        print("Erro! Operação invalida, tente umas das opções validas ou consulte o gerente.")

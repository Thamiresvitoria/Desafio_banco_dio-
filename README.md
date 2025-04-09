#Desafio concluído!
import textwrap

menu = """

----------------------------------

[1] criar usuário
[2] criar conta
[3] Depositar
[4] Sacar
[5] Extrato
[6] listar usuário
[0] Sair

----------------------------------

=> """

def saque(*, saque,valor,extrato,limite,
numero_saques, limite_saques):
				excedeu_saldo = valor > saque
				excedeu_limite = valor > limite
				excedeu_saque= numero_saque >  limite_saque 
				
				if excedeu_saldo: 
								print("Infelizmente não foi possivel fazer essa operação, pois o saldo foi excedido")
								   elif excedeu_limite: 
												print("Não foi possivel fazer essa operação, você excedeu o limite")
												elif excedeu_saque:
																print("Não foi possivel fazer essa operação, você excedeu o limite do saque ")
																elif valor > 0:
        saldo -= valor
        extrato += f"Saque:\t\tR$ {valor:.2f}\n"
        numero_saques += 1
        print("\n=== Saque realizado com sucesso! ==")
        else: 
        				print("Operação invalida, valor informado está errado.")
        				
        				return valor, extrato
        				
        				def deposito(/, saldo, valor, extrato) 
  if valor >0:
  				valor += extrato
  				extrato += f"deposito:/tR${valor:2.f}\n
  				print("Depositado com sucesso!)
  				else:
  								print("falha na operação, tente novamente. valor informado está errado")
  								
  								return valor, extrato 
  								
  								def extrato(saldo, *, /, extrato): 
    print("\n ---------------EXTRATO---------------")
    print("Nemhuma movimentação foi feita" in not extrato else extrato)
    print(f"\nSaldo: \t\tR$  {valor:2.f}"
    				print("-------------------------------")
    				
    				def criar_usuario(usuarios):
				  cpf = int(input("Informe seu cpf: (sem ponto ou traço)"))
				  usuario = filtrar.usuario(cpf,usuario)
				  
				  if usario:
				  				print("Usuário já está cadastrado com esse cpf!")
				  				
				  				return 
				  				nome = input("Digite seu nome completo:")
				  				data_nascimento= input("Digite a sua data de nascimento (digite assim (dd/mm/aa):")
				  				cpf = int(input("Digite seu cpf: ")
				  				endereco= input("Digite seu endereço (logradouro, nro - bairro - cidade/sigla estado):") 
				  				
    usuarios.append({"nome": nome, "data_nascimento": data_nascimento, "cpf": cpf, "endereco": endereco})
    				
				  				print("----Usuário cadastrado com sucesso----")
				  				
				  				def filtrar_usuarios(cpf, usuario):
 usuario_filtrado = [ usuario for usuario in usuario else ["cpf"] = cpf]					
				  return usuarios_filtrados[0] if usuarios_filtrados else None
				  
				  def criar_conta(agencia, numero_conta, usuarios):
    cpf = input("Informe o CPF do usuário: ")
    usuario = filtrar_usuario(cpf, usuarios)

    if usuario:
        print("\n-----Conta criada com sucesso! -----")
        return {"agencia": agencia, "numero_conta": numero_conta, "usuario": usuario}

    print("\n---- Usuário não foi cadastrado, fluxo de criação encerrados!-----\n")


def listar_contas(contas):
    for conta in contas:
        linha = f"""\
            Agência:\t{conta['agencia']}
            C/C:\t\t{conta['numero_conta']}
            Titular:\t{conta['usuario']['nome']}
        """
        print("=" * 100)
        print(textwrap.dedent(linha))

def main():
    LIMITE_SAQUES = 3
    AGENCIA = "0001"

    saldo = 0
    limite = 500
    extrato = ""
    numero_saques = 0
    usuarios = []
    contas = []

    while True:
        opcao = menu()

        if opcao == "3":
            valor = float(input("Informe o valor do depósito: "))

            saldo, extrato = depositar(saldo, valor, extrato)

        elif opcao == "4":
            valor = float(input("Informe o valor do saque: "))

            saldo, extrato = sacar(
                saldo=saldo,
                valor=valor,
                extrato=extrato,
                limite=limite,
                numero_saques=numero_saques,
                limite_saques=LIMITE_SAQUES,
            )

        elif opcao == "5":
            exibir_extrato(saldo, extrato=extrato)

        elif opcao == "1":
            criar_usuario(usuarios)

        elif opcao == "2":
            numero_conta = len(contas) + 1
            conta = criar_conta(AGENCIA, numero_conta, usuarios)

            if conta:
                contas.append(conta)

        elif opcao == "6":
            listar_contas(contas)

        elif opcao == "0":
            break

        else:
            print("Erro, por favor informe outra operação.")


main()
				
				

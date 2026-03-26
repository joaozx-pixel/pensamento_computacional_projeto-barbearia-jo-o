# Banco de dados temporário (Lista de dicionários)
agenda = []

while True:
    print("\n" + "="*25)
    print("   GESTÃO DA BARBEARIA")
    print("="*25)
    print("1. Agendar Cliente")
    print("2. Ver Agenda")
    print("3. Mudar Serviço")
    print("4. Cancelar Agendamento")
    print("5. Relatório de Ganhos")
    print("0. Sair")
    
    escolha = input("\nEscolha a opção: ")

    # --- 1. AGENDAR CLIENTE ---
    if escolha == '1':
        nome = input('Nome do cliente: ')
        
        print("\nServiços: [1] Corte (R$30) | [2] Barba (R$20) | [3] Combo (R$50)")
        serv_opcao = input('Escolha o serviço (1/2/3): ')
        
        if serv_opcao == '1':
            servico = "Corte de Cabelo"
            valor = 30.0
        elif serv_opcao == '2':
            servico = "Barba"
            valor = 20.0
        elif serv_opcao == '3':
            servico = "Corte e Barba"
            valor = 50.0
        else:
            print("Serviço inválido!")
            continue

        horario = input('Horário desejado: ')
        
        print("\nBarbeiros disponíveis: [1] Felipe | [2] Paulo | [3] João")
        barb_opcao = input('Escolha o barbeiro: ')
        barbeiros = {"1": "Felipe", "2": "Paulo", "3": "João"}
        barbeiro = barbeiros.get(barb_opcao, "Não definido")

        # Salva o agendamento na lista
        novo_agendamento = {
            "cliente": nome,
            "servico": servico,
            "horario": horario,
            "valor": valor,
            "barbeiro": barbeiro
        }
        agenda.append(novo_agendamento)
        print(f'\n✅ Sucesso: {nome} agendado com {barbeiro} às {horario}!')

    # --- 2. VER AGENDA ---
    elif escolha == '2':
        print('\n--- AGENDA ATUAL ---')
        if not agenda:
            print("Nenhum agendamento encontrado.")
        else:
            for i, item in enumerate(agenda):
                print(f"{i+1}. {item['horario']} - {item['cliente']} ({item['servico']}) | Barbeiro: {item['barbeiro']}")

    # --- 3. MUDAR SERVIÇO ---
    elif escolha == '3':
        nome_busca = input('Digite o nome do cliente para alterar: ')
        encontrado = False
        for agend in agenda:
            if agend['cliente'].lower() == nome_busca.lower():
                novo = input('Novo serviço (Corte/Barba/Combo): ')
                agend['servico'] = novo
                print("✅ Serviço atualizado!")
                encontrado = True
                break
        if not encontrado:
            print("❌ Cliente não encontrado.")

    # --- 4. CANCELAR ---
    elif escolha == '4':
        nome_cancelar = input('Nome do cliente para cancelar: ')
        for agend in agenda:
            if agend['cliente'].lower() == nome_cancelar.lower():
                agenda.remove(agend)
                print("✅ Agendamento removido!")
                break

    # --- 5. RELATÓRIO ---
    elif escolha == '5':
        total = sum(item['valor'] for item in agenda)
        print(f'\n--- RELATÓRIO ---')
        print(f'Total de atendimentos: {len(agenda)}')
        print(f'Faturamento previsto: R$ {total:.2f}')

    # --- 0. SAIR ---
    elif escolha == '0':
        print('Saindo do sistema...')
        break

    else:
        print('Opção inválida!')
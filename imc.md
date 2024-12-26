def calcular_imc():
    try:
        # Solicita os dados do usuário
        altura = float(input("Digite sua altura (em metros): "))
        peso = float(input("Digite seu peso (em kg): "))

        if altura <= 0 or peso <= 0:
            print("Altura e peso devem ser valores positivos.")
            return

        # Calcula o IMC
        imc = peso / (altura ** 2)

        # Classificação do IMC
        if imc < 18.5:
            classificacao = "baixo peso"
            recomendacao = "Recomendado procurar um médico para avaliação criteriosa."
        elif 18.5 <= imc <= 24.9:
            classificacao = "peso adequado"
            recomendacao = "Tudo indica que está tudo bem, mas é importante avaliar outros parâmetros da composição corporal."
        elif 25.0 <= imc <= 29.9:
            classificacao = "sobrepeso"
            recomendacao = "Atenção! Consulte um médico e reveja hábitos para reverter o quadro."
        elif 30.0 <= imc <= 34.9:
            classificacao = "obesidade grau I"
            recomendacao = "Importante buscar orientação médica e nutricional para entender melhor o seu caso."
        elif 35.0 <= imc <= 39.9:
            classificacao = "obesidade grau II"
            recomendacao = "Indica um quadro mais evoluído. Não atrase a busca por orientação médica e nutricional."
        else:  # IMC >= 40.0
            classificacao = "obesidade grau III"
            recomendacao = "Fundamental buscar orientação médica."

        # Exibe o resultado
        print(f"\nSeu IMC é {imc:.2f} kg/m².")
        print(f"Classificação: {classificacao}")
        print(recomendacao)

    except ValueError:
        print("Por favor, insira valores válidos para altura e peso.")

if __name__ == "__main__":
    calcular_imc()
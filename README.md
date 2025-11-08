# Pacotes

Pense em **pacotes** (_packages_) como caixas de ferramentas para o seu código. Cada pacote é uma coleção de arquivos de código Go (arquivos `.go`) que estão no mesmo diretório e trabalham juntos para oferecer funcionalidades específicas.

Eles são o principal mecanismo em Go para organizar, estruturar e reutilizar código.

## Pontos-chave sobre pacotes

- **Organização:**  
  Em vez de ter um único arquivo gigante com todo o seu programa, você pode dividir o código em pacotes lógicos. Por exemplo, um pacote para lidar com o banco de dados (`database`), outro para a lógica da web (`weblib`), e assim por diante.

- **Reutilização:**  
  Você pode escrever uma função útil em um pacote e, em seguida, _importar_ esse pacote em outros programas para usar essa função, sem precisar copiar e colar o código.

- **Namespace (Espaço de Nomes):**  
  Pacotes evitam conflitos de nomes. Você pode ter uma função chamada `Calcular` em um pacote `financas` e outra função também chamada `Calcular` em um pacote `fisica`. Você as acessaria como `financas.Calcular()` e `fisica.Calcular()`, sem que uma interfira na outra.

- **Visibilidade (Público vs. Privado):**  
  Go tem uma regra muito simples para controlar o que pode ser acessado de fora de um pacote:
    - **Exportado (Público):** Se um nome (de variável, função, tipo, etc.) começa com uma letra maiúscula, ele pode ser acessado por outros pacotes que o importam. Exemplo: `fmt.Println`. O `P` de `Println` é maiúsculo, por isso podemos usá-lo.
    - **Não Exportado (Privado):** Se o nome começa com uma letra minúscula, ele só pode ser usado dentro do seu próprio pacote. É uma função ou variável "interna".
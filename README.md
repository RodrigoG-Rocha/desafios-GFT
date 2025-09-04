# desafios-GFT
 ----------Itens de Estoque:----------

 
 using System;

class Program
{
    static void Main(string[] args)
    {
        ItemEstoque item = new ItemEstoque("Caneta Azul", 50);

        item.Retirar(10);

        item.ExibirDados();
    }
}

class ItemEstoque
{
    private string Nome { get; set; }
    private int Quantidade { get; set; }

    public ItemEstoque(string nome, int quantidadeInicial)
    {
        Nome = nome;
        Quantidade = quantidadeInicial;
    }

    public void Retirar(int quantidade)
    {
        if (quantidade <= Quantidade)
        {
            Quantidade -= quantidade;
            Console.WriteLine($"{quantidade} unidade(s) retirada(s) do estoque.");
        }
        else
        {
            Console.WriteLine("Não há estoque suficiente para retirar essa quantidade!");
        }
    }

    public void ExibirDados()
    {
        Console.WriteLine($"Item: {Nome}, Quantidade: {Quantidade}");
    }
}


----------Representar----------


using System;

class Pessoa
{
    public string Nome { get; set; }

    public Pessoa(string nome)
    {
        Nome = nome;
    }

    public virtual void Saudacao()
    {
        Console.WriteLine($"Olá, sou {Nome}.");
    }
}

class Cliente : Pessoa
{
    public int NumeroFidelidade { get; set; }

    public Cliente(string nome, int numeroFidelidade) : base(nome)
    {
        NumeroFidelidade = numeroFidelidade;
    }

    public override void Saudacao()
    {
        Console.WriteLine($"Olá, sou {Nome}, cliente número {NumeroFidelidade}.");
    }
}

class Program
{
    static void Main()
    {
        Cliente cliente = new Cliente("Clara", 1234);

        cliente.Saudacao();
    }
}

Prompt: Crie uma classe em C# chamada AplicativoMobile para gerenciar um projeto, com as seguintes características:

Atributos:
Nome do projeto.
Orcamento do projeto (ex: 5000.00).
NumeroMembros da equipe.

Métodos:
Permitir acessar e modificar os dados do projeto.

Validar que:
O Orcamento seja positivo.
O NumeroMembros seja positivo.
Calcular o orçamento médio por membro (Orcamento / NumeroMembros).

O código deve:
Incluir comentários explicativos. Seguir boas práticas de POO (encapsulamento, propriedades, métodos claros). O código deve ser funcional e testável.

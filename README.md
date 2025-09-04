# desafios-GFT
 --Itens de Estoque:--  
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

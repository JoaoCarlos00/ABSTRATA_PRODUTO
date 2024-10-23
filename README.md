# CLASSE ABSTRATA 2

Segundo exercício sobre classe Abstrata

## 🚀 Enunciado

Crie a classe Produto que possui os atributos nome, preço de custo e preço de venda. Possui também o método concreto calcularLucro.

A classe ProdutoAlimenticio é derivada de Produto e possui os atributos data de validade e informações nutricionais.

A classe ProdutoVestuario possui os atributos tamanho, cor e material.

Todas as classes devem ter métodos para salvar, deletar e atualizar registros em um banco de dados relacional.

### 📋 Código

package Produto;

	abstract class Produto { //Classe abstrata que irá fornecer as demais classes que, irão derivar dela, as estrutauras básicas no caso nome, preço de custo e venda
	    protected String nome;
	    protected double precoCusto;
	    protected double precoVenda;
	
	    public Produto(String nome, double precoCusto, double precoVenda) {
	        this.nome = nome;
	        this.precoCusto = precoCusto;
	        this.precoVenda = precoVenda;
 }
	
	    public double calcularLucro() { //Calculo do lucro fazendo a subtração do preço de venda com o de custo
	        return precoVenda - precoCusto;
 }
	
	    public abstract void salvar(); //Metódos abstratos para garantir que todas as subclasses de Produto forneçam suas próprias implementações para como um produto deve ser salvo, deletado e atualizado.
	    public abstract void deletar();
	    public abstract void atualizar();
}
	class ProdutoAlimenticio extends Produto { //Primeira Classe criada derivada de produto que adiciona em sua estrutura a data de validade e informações nutricionais além da estrutra puxada de produtos
	    private String dataValidade;
	    private String informacoesNutricionais;

	    public ProdutoAlimenticio(String nome, double precoCusto, double precoVenda, String dataValidade, String informacoesNutricionais) {
	        super(nome, precoCusto, precoVenda);
	        this.dataValidade = dataValidade;
	        this.informacoesNutricionais = informacoesNutricionais;
	    }

	    @Override
	    public void salvar() {
	       
	        System.out.println("Salvando produto alimentício: " + nome); //Comando para salvar no banco de dados
	    }

	    @Override
	    public void deletar() {
	        
	        System.out.println("Deletando produto alimentício: " + nome); //Comando para deletar no banco de dados
	    }

	    @Override
	    public void atualizar() {
	        
	        System.out.println("Atualizando produto alimentício: " + nome); //Comando para atualizar no banco de dados
	    }
	}
	class ProdutoVestuario extends Produto { //Segunda Classe derivada de produto que adiciona em sua estrutura tamanho, cor e material além da estrutra puxada de produtos
	    private String tamanho;
	    private String cor;
	    private String material;

	    public ProdutoVestuario(String nome, double precoCusto, double precoVenda, String tamanho, String cor, String material) {
	        super(nome, precoCusto, precoVenda);
	        this.tamanho = tamanho;
	        this.cor = cor;
	        this.material = material;
	    }

	    @Override
	    public void salvar() {
	        
	        System.out.println("Salvando produto de vestuário: " + nome); //Comando para salvar no banco de dados
	    }

	    @Override
	    public void deletar() {
	        
	        System.out.println("Deletando produto de vestuário: " + nome); //Comando para deletar no banco de dados
	    }

	    @Override
	    public void atualizar() {
	        
	        System.out.println("Atualizando produto de vestuário: " + nome); //Comando para atualizar no banco de dados
	    }
	

	    public static void main(String[] args) { //Criação de exemplos com os metodos salvar, atualizar e deletar
	        ProdutoAlimenticio produtoAlim = new ProdutoAlimenticio("Maçã", 1.0, 2.0, "08/04/2025", "60 kcal por 100g");
	        ProdutoVestuario produtoVest = new ProdutoVestuario("Camisa", 20.0, 50.0, "M", "Azul", "Algodão");

	        produtoAlim.salvar();
	        produtoVest.salvar();

	        System.out.println("Lucro da maçã: " + produtoAlim.calcularLucro());
	        System.out.println("Lucro da camisa: " + produtoVest.calcularLucro());

	        produtoAlim.atualizar();
	        produtoVest.atualizar();

	        produtoAlim.deletar();
	        produtoVest.deletar();
	    }
	}


### 🔧 Instalação

* Explicação de como deve ser utilizado o projeto

## 🛠️ Construído com

Ferramentas utilizadas e bibliotecas

* IDE Eclipse

## 📌 Versão

* **Versão 1.0** caso seja atualizado manter a descrição inicial e inserir uma nova linha com descrição da atualização.
* **Versão 1.1** - *Refatoração* *data 09/09/24*

## ✒️ Autores

* João Carlos Ferreira de Araujo RA 248152 - AC2 de Programação Orientada à Objetos


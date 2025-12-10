class Emp:
    def __init__(self, aluno_emp, data_emp):
        self.aluno_emp = aluno_emp
        self.data_emp = data_emp
        self.livros = []
    
    def adicionar_livros(self, livros):
        if livros.strip() !="":
            self.livros.append(livros)
            print(f"Produto '{livros}' adicionado à venda.")
        else:
            print("Nome do livro inválido!")
        

    def resumo(self):
        print("\n--- RESUMO DO Emprestimo ---")
        print(f"Aluno: {self.aluno_emp}") 
        print(f"Data do empréstimo: {self.data_emp}") 
        print("Livro:")
        for p in self.livros:
            print(f"- {p}")
        print(f"Total de Livros: {len(self.livros)}")

    def remover_livros(self, livro_para_remover):
        if livro_para_remover in self.livros:
            self.livros.remove(livro_para_remover)
            print(f"Livro '{livro_para_remover}' removido do empréstimo.")
        else:
            print(f"Livro '{livro_para_remover}' não encontrado nesta lista de empréstimo.")


emp = Emp("João da Silva", "03/12/2025")

emp.adicionar_livros("Cristianismo puro e Simples")
emp.adicionar_livros("Bíblia")
emp.adicionar_livros("Efésios")
emp.adicionar_livros("Efésios")

print("\n--- Status antes da devolução ---")

emp.resumo()
emp.remover_livros(input("\nQue livro deseja remover? "))

print("\n--- Status após a devolução ---")

emp.resumo()


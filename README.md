package javax.persistence;

public class livros {
   @Id
   @GeneratedValue
   private Long isbn;
   private String titulo;
   private String autor;
   private String editora;
   private int anoPublicacao;
public String getTitulo() {
	return titulo;
}
public void setTitulo(String titulo) {
	this.titulo = titulo;
}
public String getAutor() {
	return autor;
}
public void setAutor(String autor) {
	this.autor = autor;
}
public int getAnoPublicacao() {
	return anoPublicacao;
}
public void setAnoPublicacao(int anoPublicacao) {
	this.anoPublicacao = anoPublicacao;
}
public String getEditora() {
	return editora;
}
public void setEditora(String editora) {
	this.editora = editora;
}
   
   
}
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Cadastro de Livro</title>
</head>
<body>
    <h1>Cadastro de Livro</h1>
    <form action="/salvarLivro" method="post">
        <label for="titulo">Título:</label>
        <input type="text" id="titulo" name="titulo" required><br>
        
        <label for="autor">Autor:</label>
        <input type="text" id="autor" name="autor" required><br>
        
        <label for="editora">Editora:</label>
        <input type="text" id="editora" name="editora" required><br>
        
        <label for="anoPublicacao">Ano de Publicação:</label>
        <input type="text" id="anoPublicacao" name="anoPublicacao" required><br>
        
        <label for="isbn">ISBN:</label>
        <input type="text" id="isbn" name="isbn" required><br>
        
        <button type="submit">Cadastrar</button>
    </form>
</body>
</html>

<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Lista de Livros</title>
</head>
<body>
    <h1>Lista de Livros</h1>
    <table>
        <tr>
            <th>Título</th>
            <th>Autor</th>
            <th>Editora</th>
            <th>Ano de Publicação</th>
            <th>ISBN</th>
        </tr>
        <tr th:each="livro : ${livros}">
            <td th:text="${livro.titulo}"></td>
            <td th:text="${livro.autor}"></td>
            <td th:text="${livro.editora}"></td>
            <td th:text="${livro.anoPublicacao}"></td>
            <td th:text="${livro.isbn}"></td>
        </tr>
    </table>
</body>
</html>


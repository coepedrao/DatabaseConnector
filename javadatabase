import java.sql.*;

public class DatabaseExample {
    private static final String URL = "jdbc:mysql://localhost:3306/seu_banco";
    private static final String USER = "seu_usuario";
    private static final String PASSWORD = "sua_senha";

    public static void main(String[] args) {
        try (Connection conn = DriverManager.getConnection(URL, USER, PASSWORD)) {
            System.out.println("Conexão estabelecida com sucesso!");

            criarTabela(conn);
            inserirDados(conn, "João", "joao@email.com");
            inserirDados(conn, "Maria", "maria@email.com");
            listarUsuarios(conn);
        } catch (SQLException e) {
            e.printStackTrace();
        }
    }

    private static void criarTabela(Connection conn) throws SQLException {
        String sql = "CREATE TABLE IF NOT EXISTS usuarios ("
                + "id INT AUTO_INCREMENT PRIMARY KEY,"
                + "nome VARCHAR(100),"
                + "email VARCHAR(100)"
                + ")";
        try (Statement stmt = conn.createStatement()) {
            stmt.execute(sql);
            System.out.println("Tabela criada/verificada com sucesso!");
        }
    }

    private static void inserirDados(Connection conn, String nome, String email) throws SQLException {
        String sql = "INSERT INTO usuarios (nome, email) VALUES (?, ?)";
        try (PreparedStatement pstmt = conn.prepareStatement(sql)) {
            pstmt.setString(1, nome);
            pstmt.setString(2, email);
            pstmt.executeUpdate();
            System.out.println("Usuário inserido: " + nome);
        }
    }

    private static void listarUsuarios(Connection conn) throws SQLException {
        String sql = "SELECT * FROM usuarios";
        try (Statement stmt = conn.createStatement(); ResultSet rs = stmt.executeQuery(sql)) {
            System.out.println("\nLista de usuários:");
            while (rs.next()) {
                System.out.println(rs.getInt("id") + ": " + rs.getString("nome") + " - " + rs.getString("email"));
            }
        }
    }
}

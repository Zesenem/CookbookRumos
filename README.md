
 #####                                                         #    ######  ### 
#     #  ####   ####  #    # #####   ####   ####  #    #      # #   #     #  #  
#       #    # #    # #   #  #    # #    # #    # #   #      #   #  #     #  #  
#       #    # #    # ####   #####  #    # #    # ####      #     # ######   #  
#       #    # #    # #  #   #    # #    # #    # #  #      ####### #        #  
#     # #    # #    # #   #  #    # #    # #    # #   #     #     # #        #  
 #####   ####   ####  #    # #####   ####   ####  #    #    #     # #       ###


Dados Seed
Para facilitar os testes, os seguintes utilizadores estão pré-carregados na aplicação:

Utilizador Registado
Email: user@mail.com
Password: 123456
Administrador
Email: admin@mail.com
Password: 123456

----------------------------------------------------------------------------------------------------------

1. Abra o projecto.

2. Execute o seguinte comando no Package Manager Console para aplicar as migrações: Update-Database

3. Certifique-se de que a aplicação está configurada para usar o ambiente de desenvolvimento correto.

----------------------------------------------------------------------------------------------------------

Camada Modelo (Entidades)
1. User
Id: Identificador único do utilizador.
Name: Nome do utilizador.
Email: Endereço de email do utilizador.
Password: Senha do utilizador (criptografada).
Role: Enumeração que define o papel do utilizador (Convidado, Utilizador Registado, Administrador).
FavoriteRecipes: Lista de receitas favoritas do utilizador.
Comments: Lista de comentários feitos pelo utilizador.
IsBlocked: Indica se o utilizador está bloqueado (valor padrão: false).

2. Recipe
Id: Identificador único da receita.
Name: Nome da receita.
Instructions: Instruções para preparar a receita.
Ingredients: Ingredientes necessários para a receita.
CategoryId: Identificador da categoria à qual a receita pertence (chave estrangeira).
Category: Objeto da categoria associada à receita.
Difficulty: Nível de dificuldade da receita.
Duration: Tempo necessário para preparar a receita (em minutos).
Comments: Lista de comentários sobre a receita.
Ratings: Coleção de classificações dadas à receita.
Favorites: Lista de favoritos relacionados à receita.
IsApproved: Indica se a receita foi aprovada (valor padrão: false).
SubmissionDate: Data em que a receita foi submetida.

3. UserLogin
Email: Endereço de email do utilizador.
Password: Senha do utilizador.

4. Rating
Id: Identificador único da classificação.
Stars: Número de estrelas (avaliado pelo utilizador).
RecipeId: Identificador da receita avaliada (chave estrangeira).
Recipe: Objeto da receita associada à avaliação.
UserId: Identificador do utilizador que fez a avaliação (chave estrangeira).
User: Objeto do utilizador que fez a avaliação.

5. Favorite
Id: Identificador único do favorito.
RecipeId: Identificador da receita favorita (chave estrangeira).
Recipe: Objeto da receita associada ao favorito.
UserId: Identificador do utilizador que marcou a receita como favorita (chave estrangeira).
User: Objeto do utilizador que fez o favor.

6. Comment
Id: Identificador único do comentário.
Content: Texto do comentário.
CreatedAt: Data e hora em que o comentário foi criado.
RecipeId: Identificador da receita comentada (chave estrangeira).
Recipe: Objeto da receita associada ao comentário.
UserId: Identificador do utilizador que fez o comentário (chave estrangeira).
User: Objeto do utilizador que fez o comentário.

7. Category
Id: Identificador único da categoria.
Name: Nome da categoria.
Recipes: Lista de receitas que pertencem a esta categoria.

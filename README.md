<h1>Compte Rendu du projet de l'activité pratique 5 intitulé digital ebanking</h1>
  Réalisée par:Qnais Asmaa
  <h3>Plan</h3>
  <ul>
 <li> Partie 1 : Couche DAO</li>
 <li>Partie 2 : Couche service, DTOs et RestController</li>
 <li>Partie 3 et 4 : Client Angular</li>
 </ul>
 On souhaite créer une application qui permet de gérer des comptes bancaires. chaque compte appartient à un client. un compte peut subir plusieurs opérations de type DEBIT ou CREDIT. Il existe deux types de comptes : Comptes courants et comptes épargnes.
  <h3> Partie 1 : Couche DAO</h3>
  Le principe du pattern DAO est de séparer la couche modèle d'une application en deux sous-couches distinctes :

une couche gérant les traitements métier appliqués aux données, souvent nommée couche service ou métier. Typiquement, tout le travail de validation réalisé dans nos objets InscriptionForm et ConnexionForm en fait partie ;
une couche gérant le stockage des données, logiquement nommée couche de données. Il s'agit là des opérations classiques de stockage : la création, la lecture, la modification et la suppression. Ces quatre tâches basiques sont souvent raccourcies à l'anglaise en CRUD.
Pour réaliser efficacement une telle opération, il est nécessaire d'encapsuler les exceptions spécifiques au mode de stockage dans des exceptions personnalisées et propres à la couche DAO. Dans notre cas par exemple, nous allons devoir faire en sorte que les exceptions propres à SQL ou à JDBC ne soient pas vues comme telles par nos objets métier, mais uniquement comme des exceptions émanant de la « boîte noire » qu'est notre DAO.

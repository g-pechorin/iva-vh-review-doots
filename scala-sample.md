
<!-- 
pandoc scala-sample.md --listings  -f markdown -t latex -o scala-sample.md.tex
-->
```scala
import doobie._
import doobie.implicits._
import cats.effect.IO
import scala.concurrent.ExecutionContext

implicit val cs = IO.contextShift(ExecutionContext.global)

val xa = Transactor.fromDriverManager[IO](
  "org.postgresql.Driver", "jdbc:postgresql:world", "postgres", ""
)

case class Country(code: String, name: String, population: Long)

def find(n: String): ConnectionIO[Option[Country]] =
  sql"select code, name, population from country where name = $n".query[Country].option
```
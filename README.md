import androidx.appcompat.app.AppCompatActivity
import android.os.Bundle
import android.widget.TextView

class MainActivity : AppCompatActivity() {

    var Animals_List = mutableListOf<Any>()

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)
   
        Animals_List.add(Herbivore("Жираф",  5))   //Помещаем 2 травоядных животных в список
        Animals_List.add(Herbivore("Слон",   3))
        
        Animals_List.add(Carnivorous("Тигр", 200)) //Помещаем 2 плотоядных животных в список
        Animals_List.add(Carnivorous("Лев",  250))

        val MyViwe: TextView = findViewById(R.id.View_Text)
        MyViwe.text = Animals_List.toString()                    // Выводим список на экран
    }

    data class Carnivorous(var Animals: String, var Weight: Int) // класс для плотоядных животных
    data class Herbivore  (var Animals: String, var Height: Int) // класс для травоядных животных
    }

Aplikacja Spring Boot: HelloController

Ten projekt prezentuje prostą aplikację webową napisaną w Spring Boot, która wykorzystuje kontroler oraz Thymeleaf do renderowania dynamicznych treści HTML.

HelloController obsługuje dwa endpointy:
  Zwraca prosty komunikat powitalny.
  Renderuje spersonalizowane powitanie z wykorzystaniem parametru `name`.
  Integracja z Thymeleaf do dynamicznego renderowania szablonów HTML.
  Przykładowy szablon HTML wyświetlający powitanie oraz obraz.

Wymagania
- Java 17 lub nowsza
- Maven 3.6 lub nowszy
- Spring Boot (wersja kompatybilna z używanymi zależnościami)

Struktura projektu

Główny Kontroler: `HelloController.java`

package pl.edu.vistula.first_project_java_spring.HelloController;

import org.springframework.stereotype.Controller;
import org.springframework.ui.Model;
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.RequestParam;

@Controller
public class HelloController {

    @GetMapping(value = "/")
    public String hello() {
        return "Hello Vistula, in my first Spring controller.";
    }

    @GetMapping("/greeting")
    public String greeting(@RequestParam(name = "name", required = false, defaultValue = "World") String name, Model model) {
        model.addAttribute("name", name);
        return "greeting";
    }
}
![Zrzut ekranu 2025-01-26 001012](https://github.com/user-attachments/assets/90fe096d-1596-4c7d-919f-d7e98f8fb530)


#include <SFML/Graphics.hpp>

int main()
{
	sf::RenderWindow window(sf::VideoMode({800, 600}), "Lessons_1");
	window.setFramerateLimit(60);
	//тут задаем фигуры
	sf::RectangleShape rectangle({120.0f,80.0f});
	rectangle.setFillColor(sf::Color::Magenta);
	rectangle.setPosition({ 250.0f, 160.0f });
	
	sf::CircleShape triangle(90.0f, 8);
	triangle.setFillColor(sf::Color::Cyan);
	triangle.setPosition({ 400.0f, 250.0f });

	sf::CircleShape cirle(20.f);
	while (window.isOpen())
	{
		while (const auto event = window.pollEvent())
		{
			if (event->is<sf::Event::Closed>())
			{
				window.close();
			}
			if (const auto* mouse = event->getIf<sf::Event::MouseButtonPressed>())
			{
				sf::Vector2 position(mouse->position); //место нажатия
				float radius = cirle.getRadius(); //текущая толщина кисточки
				cirle.setPosition({ position.x - radius, position.y - radius });
				if (mouse->button == sf::Mouse::Button::Left)
					cirle.setFillColor(sf::Color::Red);
				else if (mouse->button == sf::Mouse::Button::Right)
					cirle.setFillColor(sf::Color::Blue);
			}
		}
		//тут будет логика работы 
		if(sf::Keyboard::isKeyPressed(sf::Keyboard::Key::A))
			rectangle.move({-3.0f,0.f});
		else if (sf::Keyboard::isKeyPressed(sf::Keyboard::Key::D))
			rectangle.move({ 3.0f,0.f });
		else if (sf::Keyboard::isKeyPressed(sf::Keyboard::Key::W))
			rectangle.move({ 0.0f,-3.f });
		else if (sf::Keyboard::isKeyPressed(sf::Keyboard::Key::S))
			rectangle.move({ 0.0f,3.f });
		window.clear(sf::Color::Black);




		//тут будет рендор того, что зададим
		window.draw(rectangle);
		window.draw(triangle);
		window.draw(cirle);
		window.display();
	}
}

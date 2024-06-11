#include<SFML/Graphics.hpp>
#include<SFML/Window.hpp>
#include<vector>
#include<cstdlib>
#include<ctime>

//constantes del juego
const int WIDTH = 800;
const int HEIGHT = 600;
const int PLAYER_SIZE = 30;
const int ENEMY_SIZE = 30;
const int BULLET_SIZE = 5;
const int ENEMY_SPEED = 2;
const int BULLET_SPEED = 5;

//Estructura para el jugador
struct Player{
    sf::Rectangleshape shape;
    int speed;
};

//Estructura para los enemigos
struct Enemy{
    sf::Rectangleshape shape;
    int speed;
};

//Estructura para las balas
struct bullet{
    sf::Rectangleshape shape;
    int speed
};

int main(){
    // Inicializar SFML
    sf::RenderWindow window(sf::VideoMode(WIDTH, HEIGHT),"Galaga");
    sf::Event event;

    //Inicializar al jugador
    Player player;
    player.shape.setSize(sf::Vector2f(PLAYER_SIZE, PLAYER_SIZE));
    player.shape.setPosition(WIDTH / 2, HEIGH - Player_SIZE * 2);
    player.speed = 5;

    //Inicializar enemigos
    std::vector<Enemy>enemies;
    for(int i = 0; i < 5; i++){
        Enemy enemy;
        enemy.shape.setSize(sf::Vector2f(ENEMY_SIZE, ENEMY_SIZE));
        enemy.shape.stPosition(rand()%(WIDTH - ENEMY_SIZE), rand() % (HEIGH / 2));
        enemy.speed = ENEMY_SPEED;
        enemies.push_black(enemy);
    }

   //inicializar balas
   std::vector<bullet>bullets;

   //Inicializar puntuacion y vidas
   int score = 0;
   int lives = 3;

  //Bucle principal del juego
  while (window.isOpen()){
    //Procesar eventos
    whilw (window.pollEvent(event)){
        if (event.type = sf::Event::closed){
            Window.close();
        }
    }

    //Mover jugador
    if(sf::Keyboard::isKeyPressed(sf::Keyboard::Left)){
        player.shape.move(-player.speed, 0);
    }
     if(sf::Keyboard::isKeyPressed(sf::Keyboard::Right)){
        player.shape.move(-player.speed, 0);
  }
   if(sf::Keyboard::isKeyPressed(sf::Keyboard::space)){
      Bullet bullet;
      bullet.shape.setSize(sf::Vector2f(BULLET_SIZE,BULLET_SIZE));
      bullet.shape.setposittion(player.shape.getPosition().x + PLAYER_SIZE/ 2, player.shape.getposition().y);
      bullet.speed = BULLET_SPEED;
      bullets.push_back(bullet);
     }

     //Mover enemigos
     for(auto& enemy : enemies){
        enemy.shape.move(0, enemy.speed);
        if(enemy.shape.getPosittion().y < HEIGHT){
            enemy.shape.setPosition(rand() % (WIDTH - ENEMY_SIZE), 0);
        }
     }

     //Mover balas
     for(auto& bullet : bullets) {
        bullet.shape.move(0, -bullet.speed);
        if(bullet.shape.getPosittion().y < 0){
            bullets.erase(std::remove(bullets.begin(),bullets.end(), bullet), bullets.end());
        }
     }
     //Chequear colisiones
     for(auto& enemy : enemies){
        for(auto& bullet : bullets){
            if(enemies.shape.getGlobelBounds().intersects(bullet.shape.getGlobalBounds())){
                score++;
                enemies.erase(std::remove(enemies.begin(,enemis.end(), enemy),enemies.end());
            }
        }
     }
     //Dibujar todo
     window.clear();
     window.draw(player.shape);
     for(auto& enemy : enemies){
        window.draw(enemy.shape);
     }
     for(auto& bullet : bullets){
        window.draw(bullet.shape);
     }
     window.display();
}
 return 0;
}
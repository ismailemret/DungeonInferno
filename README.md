# ⛓️ Dungeon Inferno
A 2D top-down dungeon crawler developed using **HTML5 Canvas** and **Vanilla JavaScript**, featuring procedural map generation and turn-based combat mechanics.  
This project was developed to implement core game programming concepts such as the game loop, procedural dungeon generation algorithms, and coordinate-based collision detection.

🎮 **Live Demo:** [Play Dungeon Inferno](https://ismailemret.github.io/DungeonInferno/)

---

## Game Screenshots

| Procedural Maze & Fog of War | Dice-Based Combat System | Player Character | Victory Screen | Guardian Encounter Screen |
|:---:|:---:|:---:|:---:|:---:|
| <img height="300" src="https://github.com/user-attachments/assets/81e44155-3763-4ce3-a7e7-93a4820cdd32" /> | <img height="300" src="https://github.com/user-attachments/assets/48823592-21ca-461a-a1fd-5ce88928b9b0" /> | <img height="300" src="https://github.com/ismailemret/DungeonInferno/blob/main/assets/images/onyeni_karakter.png" /> | <img width="350" height="227" alt="Victory Screen" src="https://github.com/user-attachments/assets/e0e3f4db-7b7e-418c-9163-c693b6c25f5d" /> | <img width="369" height="406" alt="Guardian Combat" src="https://github.com/user-attachments/assets/84edea9e-7b72-4cba-9318-bb63b363dcad" /> |

---

## Objective
The objective is to move the player step-by-step across the tiles through a dark dungeon—where only the surrounding tiles of the current position are visible—and safely navigate the maze-like layout to reach the exit tile.  
As the character progresses through the maze, various traps and hazards will be encountered.

## Tech Stack
* HTML5 Canvas
* CSS
* JavaScript
* Sound effects and music management
* Sprite-based character system

## Core Features
* **Procedural Dungeon Generation:** The `generateMap()` function builds unique rooms and corridors at the start of each game.
* **Turn-Based Combat System:** A dynamic combat screen based on dice roll probabilities that triggers upon encountering guardians.
* **Entity & Inventory Management:** Health (HP) mechanics, potion pickups, and exit reach objectives.
* **Audio Integration:** Atmospheric background music and sound effects triggered on movement and interactions.

## Technical Details
* Modular and extensible project architecture.
* **Render Engine:** A 60 FPS targeted draw loop using the Canvas API via the `draw()` function.
* **Map Algorithm:** Managed via an array (`map[]`) containing rooms dynamically generated at random coordinates based on the `roomCount` variable.
* **Entity Management:** Player, enemies, and items are stored as coordinate-based objects (`{x, y}`) with per-frame collision checks.
* **Asset Tree:** Organized directory structure for project maintainability:
  * `/assets/images/`: Character sprites and environmental textures.
  * `/assets/sounds/`: Sound effects and looping background music.

## Gameplay
While navigating the dark maze, the player may randomly encounter 4 types of hazards: oil slicks, water puddles, petroleum pools, or a much stronger obstacle—the guardian.  
Stepping onto a hazard tile triggers the dice-roll minigame inspired by *Die in the Dungeon*.  
The player starts with a fixed health of **10 HP**:
* Stepping on oil, water, or petroleum and losing the dice roll inflicts **-1 HP**.
* Encountering a guardian and losing the dice roll inflicts **-3 HP**.
* Controls: Navigate using **Arrow Keys**.
* The game starts in the center of the dungeon; overcome obstacles to reach the exit.
* You can test and inspect the game live at: https://ismailemret.github.io/DungeonInferno/

## Map Generation Algorithm
* Backtracking-inspired maze algorithm.
* 30x15 grid map generation.
* Randomly generated room placements.
* The farthest room is dynamically designated as the exit point.

## Combat System
* Dice-rolling combat mechanism.
* Fixed target values for trap hazards.
* Contested roll system against guardians.
* Health tracking and damage calculations.

## Graphics & Atmosphere
* Pixel-art visual assets.
* Dynamic fog-of-war effect.
* Animated dice-rolling mechanics.
* Sound effects for footsteps, taking damage, and victory.

## Team
* İsmail Emre Taşbilek
* Merve Nur Sayın

---

<details>
<summary>🇹🇷 <strong>Türkçe Dokümantasyon (Orijinal Metin)</strong></summary>

<br>

## Oyun Amacı
Karakteri bloklar üzerinde, karanlık ve sadece kendi bulunduğu bloğun çevresini görebileceği şekilde adım adım ilerletilerek labirent şeklindeki zindandan çıkarmak yani çıkış bloğuna varmak amaçlanır.
Karakter bu labirentte ilerlerken çeşitli tuzaklarla karşılaşır.

## Kullanılan Teknolojiler
* HTML5 Canvas
* CSS
* JavaScript
* Ses efektleri ve müzik yönetimi
* Sprite (Görsel dosya) tabanlı karakter sistemi

## Temel Özellikler
* Prosedürel Zindan Üretimi: `generateMap()` fonksiyonu, her oyun başında benzersiz odalar ve koridorlar inşa eder.
* Sıra Tabanlı Savaş Sistemi: Gardiyanlarla karşılaşıldığında devreye giren, zar olasılıklarına dayalı dinamik savaş ekranı.
* Varlık ve Envanter Yönetimi: Can (HP) sistemini etkileyen iksir (potion) toplama ve bitiş noktasına (exit) ulaşma hedefleri.
* Ses Entegrasyonu: Atmosferik fon müziği ve hareket/etkileşim anları için tetiklenen ses efektleri.

## Teknik Detaylar
* Projenin mimarisi, modüler ve genişletilebilir bir yapıdadır.
* Render Motoru: `draw()` fonksiyonu üzerinden Canvas API kullanılarak 60 FPS hedefli çizim döngüsü.
* Harita Algoritması: Zindan, `roomCount` değişkenine bağlı olarak rastgele koordinatlarda oluşturulan odaların bir veri dizisi (`map[]`) üzerinde saklanmasıyla yönetilir.
* Varlık Yönetimi: Karakter, düşmanlar ve eşyalar koordinat tabanlı nesneler olarak (`{x, y}`) saklanır ve her karede (frame) çarpışma kontrolleri yapılır.
* Dosya Yapısı:
  * `/assets/images/`: Karakter sprite'ları ve çevre görselleri.
  * `/assets/sounds/`: Ses efektleri ve döngüsel müzikler.

## Oynanış
Oyuncumuz, karanlık labirentte hareket ettirilirken karşısına 4 çeşit engelden rastgele herhangi biri çıkabilir. Bu engeller; yağ, su, petrol birikintilerinden biri veya onlardan daha güçlü bir engel olan gardiyan olabilir.
Oyuncu bu tuzaklara sahip olan bloklara yanlışlıkla basarsa karşısına ‘Die in the Dungeon’ den referans alınan zar oyunu çıkar.
Karakterin en başta sabit ve ‘10’ olan bu canına; yağ, su, petrol birikintilerinden birine basarsa ve zar oyununda kaybederse ‘-1’, gardiyanla karşılaşır ve zar oyununda kaybederse ‘-3’ puan yansır.

* Karakter ok tuşlarıyla hareket eder.
* Bir zindanın ortasında başlar ve labirentte engelleri aşarak çıkışa ulaşmaya çalışır.
* Oyunu önden inceleyebilmek için https://ismailemret.github.io/DungeonInferno/ sitesine gidebilirsiniz.

## Harita Oluşturma Algoritması
* Backtracking benzeri labirent algoritması kullanıldı
* 30x15 boyutunda harita oluşturuldu
* Odalar rastgele üretildi
* En uzak oda çıkış noktası olarak seçildi

## Savaş Sistemi
* Zar atma mekanizması ile çatışma
* Tuzaklarda sabit hedef değeri
* Gardiyanlarda karşılıklı zar sistemi
* Can sistemi ve hasar hesaplama

## Grafik ve Atmosfer
* Pixel-art tarzı görseller
* Dinamik sis efekti
* Animasyonlu zar sistemi
* Adım, hasar ve zafer ses efektleri

## Ekibimiz
* İsmail Emre Taşbilek
* Merve Nur Sayın

</details>

---

## References & Credits
* **Tilemap Textures:** Shutterstock. Pixelated wall stone illustrations. [Shutterstock Source](https://www.shutterstock.com/tr/search/pixelated-wall-stone?image_type=illustration)
* **Character Sprite:** Reddit user r/PixelArt. 16x16 topdown character sprite. [Reddit Post](https://www.reddit.com/r/PixelArt/comments/1krxwzk/16x16_topdown_character_sprite/)
* **Documentation & Guides:**
  * [W3Schools HTML Canvas](https://www.w3schools.com/graphics/canvas_intro.asp)
  * [MDN JavaScript Docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
  * [MDN HTML Docs](https://developer.mozilla.org/en-US/docs/Web/HTML)
* **Audio Files:**
  * [OpenGameArt Sound FX](https://opengameart.org/content/sound-fx-0)
  * [Pixabay 8-Bit Walking](https://pixabay.com/sound-effects/search/8%20bit%20walking/)
* **Inspiration:** [Die in the Dungeon](https://alarts.itch.io/die-in-the-dungeon)

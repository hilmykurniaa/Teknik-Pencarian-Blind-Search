# Teknik Pencarian Blind Search

# Tugas
1. Tentukan bagaimana algoritma BFS di atas dapat menentukan node ke 8, 6, dan 7.
2. Ubahlah method static void main sehingga bentuk tree seperti Gambar 4.5 dapat dibentuk. Kemudian tentukan bagaimana algoritma BFS dapat menemukan node 5.
   
   ![image](https://github.com/hilmykurniaa/Teknik-Pencarian-Blind-Search/assets/148704403/7a980ea6-b0f3-4282-bf03-13fcea3d74e1)
   
4. Ubahlah method static void main sehingga bentuk tree seperti Gambar 4.6 dapat dibentuk. Kemudian tentukan bagaimana algoritma BFS dapat menemukan node 9.

   ![image](https://github.com/hilmykurniaa/Teknik-Pencarian-Blind-Search/assets/148704403/3ad03d6b-eb2b-4945-ad3d-5b80c224e575)
   
6. Ubahlah kode program di atas sehingga bentuk tree seperti Gambar 4.7 dapat dibentuk. Kemudian tentukan bagaimana algoritma BFS dapat menemukan node C.

   ![image](https://github.com/hilmykurniaa/Teknik-Pencarian-Blind-Search/assets/148704403/0bf96b48-bddf-492b-88c8-1cc1ed268339)

# Jawaban
# 1. Cara algoritma BFS di atas menemukan node 8, 6, dan 7 adalah sebagai berikut:
1.	Langkah pertama algoritma BFS memulai dari node awal yaitu node 3 (n3) yang digunakan sebagai node awal yang diberikan kepada metode bfs(n3).
2.	Saat algoritma dimulai semua node dalam graf diinisialisasi dengan warna putih (WHITE), kecuali node awal (n3) yang dicat dengan warna abu-abu (GRAY) karena sedang dalam proses.
3.	Node awal (n3) memiliki jarak (distance) 0.
4.	Node-node yang langsung terhubung dengan node awal (n3) adalah node 2 (n2) dan node 4 (n4). Kedua node ini dimasukkan ke dalam antrian (queue) untuk diproses selanjutnya.
5.	Algoritma BFS akan terus melakukan iterasi selama antrian masih berisi node.
6.	Node yang sedang diproses adalah node 3 (n3) yang memiliki adjacency list yang berisi node 2 (n2) dan node 4 (n4).
7.	Node 2 (n2) dan node 4 (n4) berwarna putih (WHITE) karena belum diproses. Algoritma BFS akan mengubah warna node 2 (n2) dan node 4 (n4) menjadi abu-abu (GRAY), menghitung jaraknya, dan menetapkan node 3 (n3) sebagai node pendahulu.
•	Node 2 (n2) memiliki jarak 1 dari node awal (n3).
•	Node 4 (n4) juga memiliki jarak 1 dari node awal (n3).
8.	Node-node 2 (n2) dan 4 (n4) ditambahkan ke dalam antrian (queue) untuk diproses pada langkah berikutnya.
9.	Algoritma akan terus berlanjut dengan mengambil node-node dari antrian untuk diproses selanjutnya.
10.	Algoritma akan terus melakukan langkah serupa hingga semua node yang terhubung dalam graf telah diproses.
11.	Node-node yang telah selesai diproses akan diwarnai dengan warna hitam (BLACK).
12.	Hasil dari algoritma BFS adalah penemuan jarak terpendek dari node awal (n3) ke semua node lain dalam graf dan pengaturan node pendahulu untuk setiap node. Dengan informasi ini, Anda dapat menentukan jarak dari node awal (n3) ke node 8 (n8), node 6 (n6), dan node 7 (n7).

Node 8 (n8) terhubung dengan node 6 (n6), yang terhubung dengan node 4 (n4), yang terhubung dengan node 3 (n3). Jarak dari n3 ke n4 adalah 1, jarak dari n4 ke n6 adalah 1, dan jarak dari n6 ke n8 adalah 1. Oleh karena itu, jarak dari n3 ke n8 adalah 3.

Node 7 (n7) juga terhubung dengan node 6 (n6), yang terhubung dengan node 4 (n4), yang terhubung dengan node 3 (n3). Jarak dari n3 ke n4 adalah 1, jarak dari n4 ke n6 adalah 1, dan jarak dari n6 ke n7 adalah 1. Oleh karena itu, jarak dari n3 ke n7 juga adalah 3.

# 2.  Cara algoritma BFS dapat menemukan node 5.
Pertama ubah static void nya menjadi seperti berikut :

    public static void main(String[] args)

    {
        BS graph = new BS();
        Node n0 = new Node(0);
        Node n1 = new Node(1);
        Node n2 = new Node(2);
        Node n3 = new Node(3);
        Node n4 = new Node(4);
        Node n5 = new Node(5);
        Node n6 = new Node(6);
        
        
        // Ganti graph dan edge sesuai dengan yang diinginkan
        graph.addEdge(n0, n1);
        graph.addEdge(n0, n2);
       
        graph.addEdge(n1, n0);
        graph.addEdge(n1, n3);
        graph.addEdge(n1, n4);

        graph.addEdge(n2, n0);
        graph.addEdge(n2, n5);
        graph.addEdge(n2, n6);
       
        graph.addEdge(n3, n1);
        graph.addEdge(n3, n4);

        graph.addEdge(n4, n3);
        graph.addEdge(n4, n1);

        graph.addEdge(n5, n2);
        graph.addEdge(n5, n6);
        graph.addEdge(n5, n1);

        graph.addEdge(n6, n2);
        graph.addEdge(n6, n5);
        graph.addEdge(n6, n1);
        
        graph.bfs(n0);
    }

kode diatas memberikan output (0,d=0) (1,d=1) (2,d=1) (3,d=2) (4,d=2) (5,d=2) (6,d=2) 

Langkah-langkah BFS menemukan node 5 :
1.	Mulailah dengan memasukkan node 0 ke dalam antrian
2.	Periksa apakah node 5 ada di antrian. Node 5 belum ditemukan.
3.	Keluarkan node 0 dari antrian.
4.	Periksa semua node yang bertetangga dengan node 0. Node 1 dan 2 tidak dikunjungi.
5.	Masukkan node 1 dan 2 ke dalam antrian.
6.	Periksa apakah node 5 ada di antrian. Node 5 masih belum ditemukan.
7.	Keluarkan node 1 dari antrian.
8.	Periksa semua node yang bertetangga dengan node 1. Node 3 dan 4 tidak dikunjungi.
9.	Masukkan node 3 dan 4 ke dalam antrian.
10.	Periksa apakah node 5 ada di antrian. Node 5 masih belum ditemukan.
11.	Kembali ke node yang bertetanggaan dengan node 0 yaitu node 1 dan 2. Node 1 sudah diperiksa.
12.	Periksa semua node yang bertetangga dengan node 2. Node 5 dan 6 tidak dikunjungi.
13.	Masukkan node 5 dan 6 ke dalam antrian.
14.	Periksa apakah node 5 ada di antrian. Pada  tahap ini node 5 ditemukan.

# 3. Cara alogaritma BFS dapat menemukan node 9
Pertama ubah static void nya menjadi seperti berikut:

    public static void main(String[] args)

    {
        BS2 graph = new BS2();
        Node n1 = new Node(1);
        Node n2 = new Node(2);
        Node n3 = new Node(3);
        Node n4 = new Node(4);
        Node n5 = new Node(5);
        Node n6 = new Node(6);
        Node n7 = new Node(7);
        Node n8 = new Node(8);
        Node n9 = new Node(9);
        Node n10 = new Node(10);
        Node n11 = new Node(11);
        Node n12 = new Node(12);

        graph.addEdge(n1, n2);
        graph.addEdge(n1, n3);
        graph.addEdge(n1, n4);

        graph.addEdge(n2, n1);
        graph.addEdge(n2, n5);
        graph.addEdge(n2, n6);
        
        graph.addEdge(n3, n1);
        
        graph.addEdge(n4, n1);
        graph.addEdge(n4, n7);
        graph.addEdge(n4, n8);
        
        graph.addEdge(n5, n2);
        graph.addEdge(n5, n9);
        graph.addEdge(n5, n10);
        graph.addEdge(n5, n6);
        
        graph.addEdge(n6, n2);
        graph.addEdge(n6, n5);
        
        graph.addEdge(n7, n4);
        graph.addEdge(n7, n11);
        graph.addEdge(n7, n12);
        graph.addEdge(n7, n8);
        
        graph.addEdge(n8, n4);
        graph.addEdge(n8, n7);

        graph.addEdge(n9, n5);
        graph.addEdge(n9, n10);

        graph.addEdge(n10, n5);
        graph.addEdge(n10, n9);

        graph.addEdge(n11, n7);
        graph.addEdge(n11, n12);

        graph.addEdge(n12, n7);
        graph.addEdge(n12, n11);
        
        graph.bfs(n1);
    }

kode diatas memberikan output (1,d=0) (2,d=1) (3,d=1) (4,d=1) (5,d=2) (6,d=2) (7,d=2) (8,d=2) (9,d=3) (10,d=3) (11,d=3) (12,d=3)

1.	Mulailah dengan memasukkan node 1 ke dalam antrian.
2.	Periksa apakah node 9 ada di antrian. Node 9 belum ditemukan.
3.	Keluarkan node 1 dari antrian.
4.	Periksa semua node yang bertetangga dengan node 1. Node 2, 3 dan 4 tidak dikunjungi.
5.	Masukkan node 2, 3 dan 4 ke dalam antrian.
6.	Periksa apakah node 9 ada di antrian. Node 9 masih belum ditemukan.
7.	Keluarkan node 2 dari antrian.
8.	Periksa semua node yang bertetangga dengan node 2. Node 5 dan 6 tidak dikunjungi.
9.	Masukkan node 5 dan 6 ke dalam antrian.
10.	Periksa apakah node 9 ada di antrian. Node 9 masih belum ditemukan.
11.	Keluarkan node 5 dari antrian.
12.	Periksa semua node yang bertetangga dengan node 5. Node 9 dan 10 tidak dikunjungi.
13.	Masukkan node 9 dan 10 kedalam antrian.
14.	Periksa apakah node 9 ada di antrian. Pada tahap ini node 9 ditemukan

# 4. Cara alogaritma BFS menemukan Node C
Pertama ubah static void nya menjadi seperti berikut:

    public static void main(String[] args)

    {
        BS3 graph = new BS3();
        Node n1 = new Node('A');
        Node n2 = new Node('B');
        Node n3 = new Node('C');
        Node n4 = new Node('D');
        Node n5 = new Node('E');
        Node n6 = new Node('F');
        Node n7 = new Node('G');
        Node n8 = new Node('H');
        Node n9 = new Node('I');
        
        graph.addEdge(n1, n2);
        graph.addEdge(n1, n4);

        graph.addEdge(n2, n6);
        graph.addEdge(n2, n1);
        graph.addEdge(n2, n4);
        
        graph.addEdge(n3, n4);
        graph.addEdge(n3, n5);
        
        graph.addEdge(n4, n2);
        graph.addEdge(n4, n3);
        graph.addEdge(n4, n5);
        
        graph.addEdge(n5, n4);
        graph.addEdge(n5, n3);
        
        graph.addEdge(n6, n2);
        graph.addEdge(n6, n7);
        
        graph.addEdge(n7, n6);
        graph.addEdge(n7, n9);
        
        graph.addEdge(n8, n9);
        
        graph.addEdge(n9, n8);
        
        graph.bfs(n6);
    }

  Dan juga pada bagian yang bertuliskan int data yaitu pada public class dan public Node diganti dengan char karena kita menggunakan huruf bukan menggunakan angka

    public class BS3 {
      public enum NodeColour {
          WHITE, GRAY, BLACK
      }

      public static class Node {
          char data;
          int distance;
          Node predecessor;
          NodeColour colour;

      public Node(char data)

      {
        this.data = data;
      }

        public String toString() {
            return "(" + data + ",d=" + distance + ")";
        }
      }

kode diatas memberikan output (F,d=0) (B,d=1) (G,d=1) (A,d=2) (D,d=2) (I,d=2) (C,d=3) (E,d=3) (H,d=3) 

Langkah-langkah BFS menemukan node C:
1.	Mulaialah dengan memasukkan node F ke dalam antrian.
2.	Periksa apakah node C ada di antrian. Node C belum ditemukan.
3.	Keluarkan node F dari antrian.
4.	Periksa semua node yang bertetangga dengan node F. Node B dan G tidak dikunjungi.
5.	Masukkan node B dan G ke dalam antrian.
6.	Periksa apakah node C ada di antrian. Node C masih belum ditemukan.
7.	Keluarkan node B dari antrian.
8.	Periksa semua node yang bertetangga dengan node B. Node A dan D tidak dikunjungi.
9.	Masukkan node A dan D ke dalam antrian.
10.	Periksa apakah node C ada di antrian. Node C masih belum ditemukan.
11.	Keluarkan node A dari antrian.
12.	Periksa semua node yang bertetangga dengan node A. Tidak ada
13.	Keluarkan node D dari antrian.
14.	Periksa semua node yang bertetangga dengan node D. Node C dan E tidak dikunjungi.
15.	Masukkan node C dan E kedalam antrian.
16.	Periksa apakah node C ada di antrian. Pada tahap ini node C ditemukan.

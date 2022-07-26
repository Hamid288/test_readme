###### Nama : Abdul Hamid
###### kelas : XII RPL 1
###### no absen : 02

# modul l

Soal nomor 1
Lakukan proses instalasi framework laravel kedalam folder dengan nama masing masing.
```

composer create-project laravel/laravel penjualan
```


# modul 2
Soal nomor 1
Buatlah migration tabel kategori dengan menggunakan teknik yang telah di pelajari dalam modul ini.

langkah pertama
```
php artisan make:migration create_produk _table>
```

langkah kedua
isikan kode dibawah ini kedalam file yang di buat
```

<?php

use Illuminate\Database\Migrations\Migration;
use Illuminate\Database\Schema\Blueprint;
use Illuminate\Support\Facades\Schema;

return new class extends Migration
{
    /**
     * Run the migrations.
     *
     * @return void
     */
    public function up()
{
 schema::create('kategori', function (Blueprint $table)){
            $table->id();
            $table->string('nama');
            $table->timestamps();
        };
    }

    /**
     * Reverse the migrations.
     *
     * @return void
     */
    public function down()
    {
        Schema::dropIfExists('kategori');
    }
};
```
### Langkah kedua
```

php artisan migrate
```

Soal No.2
Berikan data dengan menggunakan seeder yang telah anda pelajari pada modul ini
```

<?php 

namespace Database/Seeder;

use Illuminate\Database\Console\Seeds\WithoutModelEvents;
use Illuminate\Database\Seeder;

class kategori extends Seeder
{
    /**
     * Run the database seeds.
     *
     * @return void
     */
    public function run()
    {
        DB::table('kategori')->insert (array(
            [
                'nama' => 'Perlemgkapan Pekolah',
            ],
            [
                'nama' => 'komputer',
            ],
            [
                'nama' => 'Mouse', => 'Accesories',
            ],
            [
                'nama' => 'Alat Tulis',
            ]
            ));
    }
}

Nama : Ahmad Aldy Hermawan
Kelas: XII RPL 1
Absen: 09

Modul 1
1. Lakukan proses instalasi framework laravel kedalam folder dengan nama masing-masing.
2. Buatlah projek pertama laravel
```
composer create-project laravel/laravel penjualan
```
modul 2
1. Buatlah migration tabel kategori dengan menggunakan teknik yang telah dipelajari dalam modul ini.
2.  Berikan data dengan menggunakan seeder yang telah anda pelajari
```
php artisan make:migration create_produk_table>
```
langkah kedua seperti berikut:
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
        Schema::create('users', function (Blueprint $table) {
            $table->id();
            $table->string('name');
            $table->string('email')->unique();
            $table->timestamp('email_verified_at')->nullable();
            $table->string('password');
            $table->rememberToken();
            $table->timestamps();
        });
    }
```
langkah 3
```
php artisan migrate
```
langkah 4
```
php artisan make:model kategori
```

```
```
soal kedua
langkah 1
```
php artisan make:seeder kategoriTableSeeder
```
selanjutnya
```
<?php

namespace Database\Seeders;

use Illuminate\Database\Console\Seeds\WithoutModelEvents;
use Illuminate\Database\Seeder;
use DB;

class kategoriTableSeeder extends Seeder
{
    /**
     * Run the database seeds.
     *
     * @return void
     */
    public function run()
    {
        DB::table('kategori')->insert(array(
            [
                'nama' => 'Perlengkapan Sekolah',
            ],
            [
                'nama' => 'Komputer',
            ],
            [
                'nama' => 'Sabun',
            ],
            [
                'nama' => 'Accesories',
            ],
            [
                'nama' => 'ATK',
            ]
            ));
    }
}
```

<?php

$host = "localhost";
$user = "ayyub";
$pass = "ayyub.07";
$db   = "ayyubcafe";

$conn = new mysqli($host, $user, $pass, $db);

if ($conn->connect_error) {
    die("Koneksi database gagal: " . $conn->connect_error);
}

$nama = $_POST['nama'];
$telepon = $_POST['telepon'];
$menu = $_POST['menu'];
$alamat = $_POST['alamat'];

$stmt = $conn->prepare(
    "INSERT INTO orders (nama, telepon, menu, alamat)
     VALUES (?, ?, ?, ?)"
);

$stmt->bind_param(
    "ssss",
    $nama,
    $telepon,
    $menu,
    $alamat
);

if ($stmt->execute()) {

    echo "<script>
        alert('Pesanan Ayyub Cafe berhasil disimpan!');
        window.location.href='index.html';
    </script>";

} else {

    echo "Pesanan gagal disimpan: " . $stmt->error;

}

$stmt->close();
$conn->close();

?>
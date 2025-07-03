<html>

<head>
  <title>Personajes FreeFire</title>
</head>
<body style="background-color: red">
<center>
    <label style="font-style: inherit;font-size: 30px ">Personajes de FreeFire</label>
    <table border="2" style="background-color: orange; color:white">
        <thead style="background-color: black">
            <tr>
                <th>Personaje</th>
                <th>Habilidad</th>
                <th>Descripcion</th>
                <th>Imagen</th>
            </tr>
        </thead>
        <tbody style="background-color: white; color: black">
            <?php
                include 'conexion.php';
                $query="select * from personajes";
                $resultado=$conexion->query($query);
                while($row=$resultado->fetch_assoc()){
            ?>
            <tr>
                <td><?php echo $row['nombre'];?></td>
                <td><?php echo $row['habilidad'];?></td>
                <td><?php echo $row['descripcion'];?></td>
                <td><img height="100px" src="data:foto/jpg;base64,<?php echo base64_encode($row['imagen']);?>"/></td>
            </tr>
            <?php
                }
            ?>
</table>
</center>
</body>

</html>

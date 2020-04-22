# proyecto1
<!DOCTYPE html>
<html>
<head>
<title>Cambio de Moneda</title>
<link rel="stylesheet" type ="text/css" hre="trabajo1/css/estilo.css">
</head>	
<body>
	<form name="formularioDatos" method="POST" action="#">
 		<p> Precio del Dolar y Euro</p>
 		<p> 1 Dolar = S/. 3.27 Soles</p>
 		<p> 1 Euro = S/. 3.84 Soles</p>
		<br/>
		 Ingrese Cantidad:
		 <input type="text" name="txtMonto" value="">
		 <br/> <br/>
		 Tipo de Cambio:
		 <select name="tipocambio[]" >
			  <option value="Soles1"selected>Dolares a Soles</option> 
			  <option value="Dolares">Soles a Dolares</option>
			  <option value="Soles2">Euros a Soles</option>
			  <option value="Euros">Soles a Euros</option>
		 </select>
		 <br/> <br/>
		 <input value="Calcular" type="submit" name="btnCalcular"/>
		 <br/> <br/>
   </form>
   <?php    
   		if (isset($_POST['btnCalcular']))
   		{
			$Monto = $_POST['txtMonto'];
			$tipo=$_POST["tipocambio"]; 
			
			
			for($i=0;$i<count($tipo);$i++){
				//echo "<br/> &nbsp; Tipo de cambio: ". $cambio." ". $tipo[$i];
				if($tipo[$i]=="Soles1"){
					$cambio = ($Monto*3.27);
					echo "<br/> &nbsp; ".$Monto." Dolares";
					echo "<br/> &nbsp; Tipo de cambio: ". $cambio." "."Soles";
				}
				elseif ($tipo[$i]=="Dolares") {
					$cambio = ($Monto/3.27);
					echo "<br/> &nbsp; ".$Monto." Soles";
					echo "<br/> &nbsp; Tipo de cambio: ". $cambio." "."Dolares";
				}
				elseif ($tipo[$i]=="Soles2") {
					$cambio = ($Monto*3.84);
					echo "<br/> &nbsp; ".$Monto." Euros";
					echo "<br/> &nbsp; Tipo de cambio: ". $cambio." "."Soles";
				}
				elseif ($tipo[$i]=="Euros") {
					$cambio = ($Monto/3.84);
					echo "<br/> &nbsp; ".$Monto." Soles";
					echo "<br/> &nbsp; Tipo de cambio: ". $cambio." "."Euros";
				}
			}
		}
	?>
</body>
</html>


# Instalação
<pre>
npm install
npm start
acessar navegador http://localhost:8000/
</pre>

# Envio de mensagem de texto via PHP
<pre>
$url = "http://localhost:8000/send-message";
$number = "551100000000";
$message = "mensagem";

$process = curl_init($url);
$data = http_build_query(['grant_type' => 'Envio WhatsApp', 'number' => $number, 'message' => $message,]);

$process = curl_init($url);
curl_setopt($process, CURLOPT_HTTPHEADER, ["Content-Type: application/x-www-form-urlencoded"]);
curl_setopt($process, CURLOPT_POST, true);
curl_setopt($process, CURLOPT_POSTFIELDS, $data);
curl_setopt($process, CURLOPT_RETURNTRANSFER, true); // Para "salvar" a resposta no curl_exec (o $resp).
$resp = curl_exec($process);
</pre>

# Envio de mensagem com imagem via PHP
<pre>
$url = "http://localhost:8000/send-media";
$file = "url da imagem";
$number = "551100000000";
$caption = "mensagem";

$process = curl_init($url);
$data = http_build_query(['grant_type' => 'Envio WhatsApp', 'number' => $number, 'caption' => $caption, 'file' => $file,]);

$process = curl_init($url);
curl_setopt($process, CURLOPT_HTTPHEADER, ["Content-Type: application/x-www-form-urlencoded"]);
curl_setopt($process, CURLOPT_POST, true);
curl_setopt($process, CURLOPT_POSTFIELDS, $data);
curl_setopt($process, CURLOPT_RETURNTRANSFER, true); // Para "salvar" a resposta no curl_exec (o $resp).
$resp = curl_exec($process);
</pre>

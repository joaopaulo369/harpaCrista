<script setup>
function copiarTexto() {
    // Seleciona o campo de texto
    var texto = "5a713fcb-6356-4aa5-b9c0-78ab9c144aa6";
    // Usa o método moderno da API Clipboard para copiar o texto
    navigator.clipboard.writeText(texto).then( () => {
        // Confirma que o texto foi copiado
        alert("A Chave Pix Foi Copiada Com Sucesso!");
    }).catch(function (err) {
        // Se houver um erro ao copiar o texto
        console.error("Erro ao copiar chave pix : ", err);
    });
}

</script>

<template>
    <header class="bg-primary text-white text-center py-3">
        <h1>Contribua com a nossa missão</h1>
    </header>

    <main class="container mt-5">
        <section class="text-center">
            <h2 class="mb-4">Como Fazer sua Doação</h2>
            <p class="lead">Sua contribuição é essencial para continuarmos nosso trabalho de tornar a Harpa Cristã
                acessível à comunidade. Veja abaixo como você pode doar:</p>
        </section>

        <div class="row mt-5">
            <div class="col-md-6">
                <div class="card border-primary mb-3">
                    <div class="card-body">
                        <p class="card-text">"Deem graças em todas as circunstâncias, pois esta é a vontade de Deus para
                            vocês em Cristo Jesus."</p>
                        <strong>1 Tessalonicenses 5:18</strong>
                    </div>
                </div>
            </div>

            <div class="col-md-6">
                <div class="card border-primary mb-3">
                    <div class="card-body text-center">
                        <h5 class="card-title">Doação Pix</h5>
                        <img class="img-thumbnail" src="../assets/img/qrCode.jpeg" alt="QrCode">
                        <button @click="copiarTexto()" class="btn btn-primary my-2 mx-auto">Copiar Chave Pix</button>
                        <p hidden class="card-text">5a713fcb-6356-4aa5-b9c0-78ab9c144aa6</p>
                    </div>
                </div>
            </div>
        </div>

        <section class="text-center mt-5">
            <h3>Entre em Contato</h3>
            <p>Se tiver dúvidas sobre como doar, entre em contato conosco pelo e-mail: <a
                    href="mailto:joaopaulo369369@gmail.com">joaopaulo369369@gmail.com</a></p>
        </section>
    </main>

</template>


<style scoped></style>
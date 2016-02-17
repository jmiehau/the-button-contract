# Pseudo-code

Importante:
- La opción de tener un histórico de todas las transacciones.
- Articular un contrato que permita ajustar el BlockNumber sobre todo al inicio.
- ¿Un contrato que permita ser actualizado?


Variables:
- Define Bounty //suma inicial. Aportada por el creador.

- Define Gamer //el último que ha hecho la transacción válida sobre el smart contract.

- Define Balance //suma del Bounty inicial más la suma de las transferencias todavía no adjudicadas.

- Define BlocksNumber //números de bloques de espera para enviar el balance al premiado.

- Define Beneficiary //Gamer que ha conseguido el Balance. Nadie ha hecho una transferencia válida dentro de los BlockNumber siguientes a su última transacción//

- Define Fee //comisión que se lleva el que hace deploy del contrato. Es una comisión en del total del Balance acumulado. Una vez que el Beneficiary cobra, el creador del contrato recibe la fee//



Funcions principales:
- Una vez que está desplegado el contrato con el Bounty inicial el contrato queda latente hasta la primera transacción.
- Si se recibe una transacción, dicha address queda reconocida como Gamer.
- Empieza una cuenta regresiva esperando a BlocksNumber (X números de bloques).
- Si otro usuario hace una nueva transacción, es el nuevo Gamer. El anterior ha perdido la opción.
- Si el Gamer ha llevado X BlocksNumber sin que le pisen la transacción. Se adjudica el Balance a su favor. A la misma eth address que origen de los fondos.
- Una fee de ese Balance va a parar al que desplegó el contrato y aportó el Bounty.

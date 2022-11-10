# Aviso de segurança para organizações criadas antes do Aragon 0.8

[Mudanças](https://github.com/aragon/aragonOS/issues/549) nas regras de consenso da rede Ethereum, que foram ativadas com o hard fork Istanbul, quebraram a funcionalidade chave na forma como as versões pré-0.8 dos contratos inteligentes do Aragon lidam com depósitos ETH de outros contratos inteligentes.

O resultado é que, após o hard fork de Istambul (ocorreu em 7 de dezembro de 2019), os depósitos ETH enviados de um contrato inteligente para contratos inteligentes do Aragon pré-0,8 falharão e a transação será revertida. **Em alguns casos, isso pode levar a uma perda permanente de fundos.** Além disso, certas funcionalidades serão quebradas, levando a uma experiência ruim para os usuários das organizações de Aragon.

As organizações criadas após o lançamento do Aragon 0.8 terão automaticamente uma correção para esse problema e nenhuma ação adicional será necessária.

<mark style="color:red;">**As organizações criadas antes do lançamento do Aragon 0.8 (11 de setembro de 2019) são aconselhadas a migrar seus ativos e membros para uma nova organização Aragon**</mark> criada usando versões pós-0.8 dos contratos de Aragon.

Você pode criar sua nova organização em [app.aragon.org](https://app.aragon.org/), configurar as permissões da nova organização para espelhar a organização antiga, transferir os membros, fundos e outros ativos para a nova organização e continuar de onde parou.

Para mais detalhes, leia [este post](https://blog.aragon.org/istanbul-hard-fork-impact/) no blog do projeto Aragon.

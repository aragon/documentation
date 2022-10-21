# Application Agent

## Qu'est-ce que l'application Agent ?

L'**application Agent** permet aux organisations d'Aragon **d'interagir** directement avec tout **autre contrat intelligent** sur Ethereum. Avant l'application Agent, une organisation devait désigner une partie de confiance pour interagir avec un contrat intelligent Ethereum en son nom.

{% hint style="info" %}
Par exemple, une organisation peut envoyer une somme de $DAI à l'un de ses employés, à qui l'on fait confiance pour prêter cette somme sur Compound, percevoir des intérêts, puis renvoyer les intérêts et le principe à l'organisation.
{% endhint %}

Désormais, avec Agent, une organisation peut prêter ses $DAI sur Compound directement, sans avoir à faire confiance à un quelconque intermédiaire.

## Comment commencer à utiliser l'application Agent ?

La manière la plus simple de commencer à utiliser l'application Agent est de **cocher la case** pour l'installer de manière facultative lors de la création de votre organisation :

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8bc80204286364bc8f9029/file-zLiYZ6kXSy.png)

{% hint style="info" %}
Notez que l'installation de l'Agent via l'un des modèles remplacera l'application Vault normalement incluse avec les modèles qui n'utilisent pas l'application Agent.
{% endhint %}

{% hint style="warning" %}
Si vous n'avez pas installé l'application Agent lors de la création de votre organisation, vous pouvez l'installer après la création de l'organisation. Pour ce faire, vous devrez suivre les instructions pour i[nstaller et initialiser l'application Agent en utilisant l'aragonCLI](https://github.com/aragon/aragon-apps) (en anglais). Notez que cette option est destinée aux experts.
{% endhint %}

## Interface frontale de l'agent

L'**application Agent** dispose actuellement **d'une interface frontale** en mode affichage uniquement, qui vous permet de voir quels jetons sont actuellement détenus par l'application Agent (y compris les jetons ERC-20, ERC-677 et ERC-777) et de consulter l'historique des transactions effectuées à l'aide de l'application Agent. L'historique des transactions peut être filtré par type de transaction, jeton ou date, et peut être exporté sous forme de fichier CSV.

![Agent App page](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5e8ce5d32c7d3a7e9aea8d19/file-r5322DPQHX.png)

L'adresse du contrat intelligent de l'agent est disponible dans le menu _**System**_ (Système) de la page  _**Organization**_.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8bcdad2c7d3a7e9ae1a16d/file-pJP6dzQfhR.png)

> <mark style="color:purple;">**Avez-vous des questions, laissez vos commentaires sur le forum Aragon**</mark><mark style="color:purple;">** **</mark><mark style="color:purple;"><mark style="color:purple;">**(**<mark style="color:purple;"></mark><mark style="color:purple;">**en anglais)**</mark>**  👇**

{% embed url="https://support.aragon.org/t/aragon-client-navigate-your-dao-agent-app/28/2" %}

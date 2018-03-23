---
title: Vytvoření prostředí pro vývoj Node.js s kontejnery pomocí Kubernetes v cloudu – krok 3 – vytvoření webové aplikace ASP.NET | Microsoft Docs
author: johnsta
ms.author: johnsta
ms.date: 02/20/2018
ms.topic: get-started-article
ms.technology: vsce-kubernetes
description: Rychlý vývoj Kubernetes s kontejnery a mikroslužeb v Azure
keywords: Docker, Kubernetes, Azure, AKS, Azure Container Service, kontejnery
manager: ghogen
ms.openlocfilehash: 26d6753bf17b459c33cd11c46186d272d477fe10
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/19/2018
---
# <a name="get-started-on-connected-environment-with-nodejs"></a>Začínáme v připojeném prostředí s Node.js

Předchozí krok: [vytvořte Kubernetes vývojového prostředí v Azure](get-started-nodejs-02.md)

## <a name="create-a-nodejs-web-app"></a>Vytvoření Node.js webové aplikace
Stáhněte si kód z Githubu přechodem na https://github.com/Azure/vsce a vyberte **klonovat nebo stáhnout** ke stahování úložiště GitHub na vašem místním prostředí. Kód pro tato příručka je v `vsce/samples/nodejs/getting-started/webfrontend`.

[!INCLUDE[](includes/vsce-init.md)]

[!INCLUDE[](includes/ensure-env-created.md)]

[!INCLUDE[](includes/build-and-run-in-k8s-cli.md)]

## <a name="update-a-content-file"></a>Aktualizace obsahu souboru
Připojené prostředí není jenom o získání kód spuštěný v Kubernetes – jde o umožňuje rychle a interaktivně, najdete v části kódu změny se projeví až v prostředí Kubernetes v cloudu.

1. Vyhledejte soubor `./public/index.html` a proveďte úpravy v kódu HTML. Například změňte stín modrou barvu pozadí stránky:

```html
<body style="background-color: #95B9C7; margin-left:10px; margin-right:10px;">
```

2. Uložte soubor. Několik okamžiků později, v okně terminálu se zobrazí zpráva, že soubor v kontejneru spuštěné byla aktualizována.
1. Přejděte do prohlížeče a aktualizujte stránku. Měli byste vidět barvu aktualizovat.

Co se stalo? Úpravy souborů obsahu, jako je HTML a CSS, není zapotřebí restartování, takže proces Node.js aktivní `vsce up` příkaz budou automaticky synchronizovat změny obsahu soubory přímo do kontejneru spuštěné v Azure, a tím poskytuje rychlý způsob, jak zobrazit vaše úpravy obsahu.

### <a name="test-from-a-mobile-device"></a>Testování z mobilního zařízení
Pokud otevřete webovou aplikaci na mobilním zařízení, si všimnete, že rozhraní nezobrazí správně na malé zařízení.

Chcete-li odstranit tento problém, přidáme `viewport` metaznačku:
1. Otevřete soubor `./public/index.html`
1. Přidat `viewport` značka meta v existující `head` element:

```html
<head>
    <!-- Add this line -->
    <meta name="viewport" content="width=device-width, initial-scale=1">
</head>
```

1. Uložte soubor.
1. Aktualizujte prohlížeč vašeho zařízení. Teď byste měli vidět webové aplikace, vykreslí správně. 

Toto je příklad, jak některé problémy právě nebyly nalezeny dokud testů na zařízení, která aplikace je určen pro použití. S VS připojené prostředí můžete rychle iterovat kódu a ověřit změny na cílovém zařízení.

## <a name="update-a-code-file"></a>Aktualizace souboru kódu
Aktualizuje se soubory kódu na straně serveru vyžaduje trochu další práci, protože aplikace Node.js je nutné restartovat.

1. V okně terminálu stiskněte `Ctrl+C` (Zastavit `vsce up`).
1. Otevření souboru kódu s názvem `server.js`a upravte služby uvítací zprávu: 

```javascript
res.send('Hello from webfrontend running in Azure!');
```

3. Uložte soubor.
1. Spustit `vsce up` v okně terminálu. 

Tím se znovu sestaví bitovou kopii kontejneru a opětovně nasadí Helm grafu. Znovu načte stránku prohlížeče a podívejte se na kód změny vstoupí v platnost.


Není dispozici i však *rychlejší metoda* pro vývoj kód, který jsme vám prozkoumat v další části. 
> [!div class="nextstepaction"]
> [Ladění kontejner v Kubernetes](get-started-nodejs-04.md)

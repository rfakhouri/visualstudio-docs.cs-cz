---
title: Testování částí kontejnerizované aplikace
author: ghogen
description: Spouštění testů jednotek s každým sestavením pro projekt Dockeru v sadě Visual Studio
ms.author: ghogen
ms.date: 06/17/2019
ms.technology: vs-azure
ms.topic: conceptual
ms.openlocfilehash: ec5aea44362cf82f6745671cc0706f80e01a60ad
ms.sourcegitcommit: 0cd282a7584b9bfd4df7882f8fdf3ad8a270e219
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/28/2019
ms.locfileid: "67467410"
---
# <a name="how-to-run-unit-tests-for-a-containerized-app"></a>Postupy: Spouštění testů jednotek pro kontejnerizované aplikace

S každým sestavením projektu kontejnerizovaných může spustit testy jednotky tak, že upravíte vašem souboru Dockerfile.

## <a name="prerequisites"></a>Požadavky

- [Desktop dockeru](https://hub.docker.com/editions/community/docker-ce-desktop-windows)
- Install [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)
- Nastavení testů jednotek pro spuštění pomocí [příkazu dotnet test](/dotnet/core/tools/dotnet-test)
- Nainstalujte [kontejnery okno rozšíření](https://aka.ms/vscontainerspreview)

## <a name="add-unit-tests-to-the-dockerfile"></a>Přidání testování součástí do souboru Dockerfile

Visual Studio nemá některých optimalizací výkonu speciální před úpravou souboru Dockerfile. Při vytváření **ladění** konfigurace sady Visual Studio sestavuje projekty v místním počítači a zkopíruje výsledek do kontejneru. Ano, je proveden pouze první fázi vícefázových soubor Dockerfile uvedené v souboru Dockerfile. Další informace najdete v tématu [proces sestavení nástroje kontejneru sady Visual Studio](container-build.md).

Přidání jednotkových testů do vícefázových soubor Dockerfile, přidejte `unit-test` fázi k souboru Dockerfile mezi `build` a `publish` fází.

```
FROM build AS unit-test
RUN dotnet unit-test --logger:trx
```

Visual Studio spustí jenom v první fázi **ladění** konfigurace, proto `unit-test` fázi spustit pouze **vydání** konfigurace. Ale i v **vydání** konfigurace, v protokolu výsledků se nezahrnuly do finální bitové kopie, protože finální image se sestavuje ze `base` fáze, nikoli z `unit-test` fázi. Pokud chcete spustit testy a vytvořit bitovou kopii, kde můžete zobrazit protokoly, použijte následující příkaz:

```cmd
docker build --target:unit-test
```

## <a name="next-steps"></a>Další kroky

Pak můžete použít [okno kontejneru](view-and-diagnose-containers.md) (Pokud máte nainstalované rozšíření) k zobrazení protokolů.  

Chcete-li zobrazit protokoly testu, použijte **Ctrl**+**Q** a vyhledejte **kontejnery** otevřít **kontejnery** okna. V **kontejnery** okně Najít kontejner, otevřete **soubory** kartu, podívejte se do výsledků testu (.trx) souboru v systému souborů kontejneru a otevřete ho chcete zobrazit výsledky v sadě Visual Studio.


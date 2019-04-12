---
title: Konfigurace nástroje kontejneru sady Visual Studio
description: Konfigurace k dispozici v sadě Visual Studio tools pro práci s kontejnery Dockeru.
author: ghogen
ms.author: ghogen
ms.topic: conceptual
ms.date: 03/20/2019
ms.technology: vs-azure
ms.openlocfilehash: 6fe51e0067ac15eb8e775786047009411c1e3181
ms.sourcegitcommit: cd91a8a4f6086cda9ba6948be25864fc7d6b8e44
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/12/2019
ms.locfileid: "59537967"
---
# <a name="how-to-configure-visual-studio-container-tools"></a>Postup konfigurace nástroje kontejneru sady Visual Studio

Pomocí nastavení aplikace Visual Studio, můžete ovládat některé aspekty toho, jak Visual Studio funguje s kontejnery Dockeru, včetně nastavení, které ovlivňují výkon a využití prostředků, při práci s kontejnery Dockeru.

## <a name="container-tools-settings"></a>Nastavení nástroje kontejneru

V hlavní nabídce zvolte **nástroje > Možnosti**a rozbalte **nástroje kontejneru sady > Nastavení**. Nastavení nástroje kontejneru se zobrazí.

::: moniker range="vs-2017"

![Visual Studio kontejnerových nástrojů možnosti zobrazení: Automaticky získat požadované Image Dockeru při načtení projektu, automaticky spustit kontejnery na pozadí, automaticky ukončit kontejnery v řešení zavřít a nechcete zobrazovat výzvu pro důvěřující certifikát SSL.](./media/overview/visual-studio-docker-tools-options.png)
::: moniker-end

::: moniker range=">=vs-2019"

Nástroje kontejneru sady **Obecné** nastavení:

![Visual Studio kontejnerových nástrojů možnosti zobrazení: Nainstalujte Docker Desktop v případě potřeby a certifikátu důvěřovat ASP.NET Core SSL.](./media/configure-container-tools/tools-options-1.png)

Nástroje kontejneru sady **jednoho projektu** a **Docker Compose** nastavení:

![Visual Studio kontejnerových nástrojů možnosti zobrazení: Ukončit kontejnery na Zavřít projekt, získat požadované Image Dockeru v projektu otevřít a spustit kontejnery na projektu otevřete.](./media/configure-container-tools/tools-options-2.png)
::: moniker-end

V následující tabulce může pomoct při rozhodování, jak nastavit tyto možnosti.

::: moniker range="vs-2017"
| Name | Výchozí nastavení | Platí pro | Popis |
| -----|:---------------:|:----------:| ----------- |
| Automaticky získat požadované Image Dockeru při načtení projektu | On | Docker Compose | Pro zvýšení výkonu při načítání projektů sady Visual Studio spustí operaci Docker pull na pozadí tak, že až budete připraveni ke spuštění kódu, se image nestáhne již nebo probíhá stahování. Pokud jste právě načítá projekty a procházení kódu, můžete to vypnout aby se zabránilo stahování imagí kontejnerů, které nepotřebujete. |
| Automaticky spustit kontejnery na pozadí | On | Docker Compose | Znovu pro zajištění zvýšeného výkonu sady Visual Studio vytvoří kontejner s připojí svazek připravené pro když sestavíte a spustíte svůj kontejner. Pokud chcete řídit, kdy se vytvoří kontejner, vypněte toto. |
| Automaticky ukončit kontejnery na řešení zavřít | On | Docker Compose | Pokud byste o ni kontejnerů pro vaše řešení, aby kontinuálně běžely po zavření řešení nebo zavření sady Visual Studio, vypnutí této funkce. |
| Nezobrazovat výzvu důvěřující certifikátu SSL pro localhost | Off | Projekty ASP.NET Core 2.1 | Pokud localhost certifikát SSL není důvěryhodný, Visual Studio zobrazí výzvu pokaždé, když spuštění projektu, pokud je toto políčko zaškrtnuté. |
::: moniker-end

::: moniker range=">=vs-2019"

Následující tabulka popisuje **Obecné** nastavení:

| Name | Výchozí nastavení | Platí pro | Popis |
| -----|:---------------:|:----------:| ----------- |
| V případě potřeby nainstalujte Docker Desktop | Zobrazit dotaz | Jeden projekt, Docker Compose | Zvolte, zda chcete být vyzváni, pokud není nainstalovaný Docker Desktop. |
| Důvěřovat certifikátu ASP.NET Core SSL | Zobrazit dotaz | Projekty ASP.NET Core 2.x | Pokud je nastavena na **řádku mě**, pokud certifikát SSL pro localhost není důvěryhodný, Visual Studio zobrazí výzvu pokaždé, když spuštění projektu. |

Následující tabulka popisuje **jednoho projektu** a **Docker Compose** nastavení:

| Name | Výchozí nastavení | Platí pro | Popis |
| -----|:---------------:|:----------:| ----------- |
| Získat požadované Image Dockeru v projektu otevřít | Pravda | Jeden projekt, Docker Compose | Pro zvýšení výkonu při načítání projektů sady Visual Studio spustí operaci Docker pull na pozadí tak, že až budete připraveni ke spuštění kódu, se image nestáhne již nebo probíhá stahování. Pokud jste právě načítá projekty a procházení kódu, můžete nastavit na **False** aby se zabránilo stahování imagí kontejnerů, není nutné. |
| Spouštění kontejnerů v projektu otevřít | Pravda | Jeden projekt, Docker Compose | Znovu pro zajištění zvýšeného výkonu sady Visual Studio vytvoří kontejner s připojí svazek připravené pro když sestavíte a spustíte svůj kontejner. Pokud chcete řídit, kdy se vytvoří kontejner, nastavte na **False**. |
| Zavřete ukončit kontejnery na projektu | Pravda | Jeden projekt a Docker Compose | Nastavte na **False** Pokud byste chtěli kontejnerů pro vaše řešení, aby kontinuálně běžely po zavření řešení nebo zavření sady Visual Studio. |

::: moniker-end
> [!WARNING]
> Pokud localhost certifikát SSL není důvěryhodný a zaškrtněte políčko pro potlačení výzvy k potvrzení, nemusí podařit HTTPS webové požadavky v době běhu ve vaší aplikaci nebo službě. V takovém případě zrušte zaškrtnutí políčka **nechcete zobrazovat výzvu** zaškrtávací políčko, spouštění vašeho projektu a označuje vztah důvěryhodnosti na řádku.

## <a name="next-steps"></a>Další kroky

Další informace o práci s kontejnery v sadě Visual Studio v tomto [přehled](visual-studio-tools-for-docker.md).
---
title: Instalace sady Visual Studio s použitím parametrů příkazového řádku
titleSuffix: ''
description: Další informace o použití parametrů příkazového řádku k řízení nebo přizpůsobit instalaci sady Visual Studio.
ms.date: 03/30/2019
ms.custom: seodec18
ms.topic: conceptual
f1_keywords:
- command-line parameters
- switches
- command prompt
ms.assetid: 480f3cb4-d873-434e-a8bf-82cff7401cf2
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.prod: visual-studio-windows
ms.technology: vs-installation
ms.openlocfilehash: 8e999df4fc1269025c9adc038c1a17dd586a3081
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62951320"
---
# <a name="use-command-line-parameters-to-install-visual-studio"></a>Instalace sady Visual Studio s použitím parametrů příkazového řádku

Při instalaci sady Visual Studio z příkazového řádku, můžete použít různé parametry příkazového řádku řídit nebo přizpůsobení instalace. Z příkazového řádku můžete provést následující akce:

- Spusťte instalaci s možnostmi předem vybrali.
- Automatizujte proces instalace.
- Vytvoření mezipaměti (rozložení) instalačních souborů pro pozdější použití.

Možnosti příkazového řádku se používají ve spojení s zaváděcí nástroj instalační program, který je soubor malé (přibližně 1MB), který zahájí proces stahování. Zaváděcí nástroj je první spustitelný soubor, který se spustí, když si stáhnete z webu Visual Studio. Chcete-li získat přímý odkaz na nejnovější verzi bootstrapper pro edici produktu, které chcete instalovat pomocí následujících odkazů:

::: moniker range="vs-2017"

- [Visual Studio 2017 Enterprise](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=enterprise&rel=15&utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=link+cta&utm_content=download+commandline+parameters+vs2017)
- [Visual Studio 2017 Professional](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=professional&rel=15&utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=link+cta&utm_content=download+commandline+parameters+vs2017)
- [Visual Studio 2017 Community](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=community&rel=15&utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=link+cta&utm_content=download+commandline+parameters+vs2017)

::: moniker-end

::: moniker range="vs-2019"

- [Visual Studio 2019 Enterprise](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=enterprise&rel=16&utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=link+cta&utm_content=download+commandline+parameters+vs2019+rc)
- [Visual Studio 2019 Professional](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=professional&rel=16&utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=link+cta&utm_content=download+commandline+parameters+vs2019+rc)
- [Visual Studio 2019 Community](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=community&rel=16&utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=link+cta&utm_content=download+commandline+parameters+vs2019+rc)

::: moniker-end

## <a name="command-line-parameters"></a>Parametry příkazového řádku

 Parametry příkazového řádku aplikace Visual Studio jsou malá a velká písmena.

> Syntaxe: `vs_enterprise.exe [command] <options>...`

(Nahradit `vs_enterprise.exe` odpovídajícím způsobem pro edici produktu instalujete.)

>[!TIP]
> Další příklady použití příkazového řádku instalace sady Visual Studio, najdete v článku [příklady parametrů příkazového řádku](command-line-parameter-examples.md) stránky.

| **Příkaz** | **Popis** |
| ----------------------- | --------------- |
| (prázdné) | Nainstaluje produkt. |
| `modify` | Upraví zobrazí nainstalovaný produkt. |
| `update` | Aktualizuje zobrazí nainstalovaný produkt. |
| `repair` | Opraví zobrazí nainstalovaný produkt. |
| `uninstall` | Odinstaluje zobrazí nainstalovaný produkt. |
| `export` | **Novinka ve verzi 15.9**: Exportuje výběr instalace na konfigurační soubor instalace. **Poznámka:** Jde použít jenom s vs_installer.exe. |

## <a name="install-options"></a>Možnosti instalace

| **Možnost instalace** | **Popis** |
| ----------------------- | --------------- |
| `--installPath <dir>` | Instalační adresář pro instance, kterou chcete použít. Pro instalačního příkazu, to je **volitelné** a nainstalovanou instanci. Pro další příkazy jde **vyžaduje** a kam se nainstaloval dříve nainstalovanou instanci. |
| `--addProductLang <language-locale>` | **Volitelné**: Při instalaci nebo upravte činnost, určuje uživatelského rozhraní jazykových sad, které jsou nainstalovány do produktu. Může se objevit více než jednou v příkazovém řádku, chcete-li přidat více jazykových sad. Pokud není k dispozici, instalace používá národní prostředí počítače. Další informace najdete v tématu [seznam národních prostředí jazyka](#list-of-language-locales) části na této stránce.|
| `--removeProductLang <language-locale>` | **Volitelné**: Při instalaci nebo upravte činnost, určuje uživatelského rozhraní jazykových sad, které budou odebrány z produktu. Může se objevit více než jednou v příkazovém řádku, chcete-li přidat více jazykových sad. Další informace najdete v tématu [seznam národních prostředí jazyka](#list-of-language-locales) části na této stránce.|
| `--add <one or more workload or component IDs>` | **Volitelné**: Jeden nebo více úloh nebo ID komponenty pro přidání. Ale ne doporučené a volitelné komponenty jsou nainstalovány požadované součásti artefaktu. Můžete určit další součásti globálně pomocí `--includeRecommended` a/nebo `--includeOptional`. Chcete-li zahrnout více úloh nebo komponenty, opakujte `--add` příkazu (například `--add Workload1 --add Workload2`). Pro citlivější ovládací prvek, můžete připojit `;includeRecommended` nebo `;includeOptional` ID (například `--add Workload1;includeRecommended` nebo `--add Workload2;includeRecommended;includeOptional`). Další informace najdete v tématu [pracovního vytížení a komponenta ID](workload-and-component-ids.md) stránky. Tato možnost podle potřeby, můžete opakovat.|
| `--remove <one or more workload or component IDs>` | **Volitelné**: Jeden nebo více úloh nebo ID komponenty odebrat. Další informace najdete v tématu naše [pracovního vytížení a komponenta ID](workload-and-component-ids.md) stránky. Tato možnost podle potřeby, můžete opakovat.|
| `--in <path>` | **Volitelné**: Identifikátor URI nebo cesta k souboru odpovědí.  |
| `--all` | **Volitelné**: Určuje, zda nainstalovat všechny úlohy a komponenty pro produkt. |
| `--allWorkloads` | **Volitelné**: Nainstaluje všechny úlohy a komponenty, žádné doporučené nebo volitelné součásti. |
| `--includeRecommended` | **Volitelné**: Obsahuje doporučené komponenty pro všechny úlohy, které jsou nainstalovány, ale nikoli volitelné komponenty. Úlohy jsou zadány buď pomocí `--allWorkloads` nebo `--add`. |
| `--includeOptional` | **Volitelné**: Zahrnuje volitelné komponenty pro všechny úlohy, které jsou nainstalovány, ale ne doporučené komponenty. Úlohy jsou zadány buď pomocí `--allWorkloads` nebo `--add`.  |
| `--quiet, -q` | **Volitelné**: Při provádění instalace nezobrazují žádné uživatelské rozhraní. |
| `--passive, -p` | **Volitelné**: Zobrazení uživatelského rozhraní, ale nikoli požadavku zásahu od uživatele. |
| `--norestart` | **Volitelné**: Pokud jsou k dispozici, příkazů s `--passive` nebo `--quiet` neprovede automatický restart počítače (v případě potřeby).  To je ignorováno, pokud žádná `--passive` ani `--quiet` jsou uvedeny.  |
| `--nickname <name>` | **Volitelné**: Definuje Přezdívka přiřadit zobrazí nainstalovaný produkt. Přezdívka nesmí být delší než 10 znaků.  |
| `--productKey` | **Volitelné**: Definuje kód product key pro zobrazí nainstalovaný produkt. Skládá se z 25 alfanumerických znaků buď ve formátu `xxxxx-xxxxx-xxxxx-xxxxx-xxxxx` nebo `xxxxxxxxxxxxxxxxxxxxxxxxx`. |
| `--help, --?, -h, -?` | Zobrazte offline verzi této stránky. |
| `--config <path>` | **Volitelné** a **novinkou 15.9**: Při instalaci nebo upravte činnost, určuje, úlohy a komponenty pro přidání založeny na konfigurační soubor instalace předtím uložili. Tato operace je additive a nedojde k odebrání jakékoli úlohy nebo komponenty, pokud nejsou k dispozici v souboru. Navíc nepřidá položky, které se nevztahují na produkt. Během operace exportu určuje umístění pro uložení konfigurační soubor instalace. |

> [!IMPORTANT]
> Při zadávání více úloh a součástí, je nutné opakovat `--add` nebo `--remove` přepínač příkazového řádku pro každou položku.

## <a name="layout-options"></a>Možnosti rozložení

| **Možnosti rozložení** | **Popis** |
| ----------------------- | --------------- |
| `--layout <dir>` | Určuje adresář, který chcete vytvořit offline instalaci mezipaměti. Další informace najdete v tématu [vytvoření síťové instalace sady Visual Studio](create-a-network-installation-of-visual-studio.md).|
| `--lang <one or more language-locales>` | **Volitelné**: Použít s `--layout` Příprava offline instalace mezipaměti pomocí balíčků prostředků se zadaným jazyk(y). Další informace najdete v tématu [seznam národních prostředí jazyka](#list-of-language-locales) části na této stránce.|
| `--add <one or more workload or component IDs>` | **Volitelné**: Jeden nebo více úloh nebo ID komponenty pro přidání. Ale ne doporučené a volitelné komponenty jsou nainstalovány požadované součásti artefaktu. Můžete určit další součásti globálně pomocí `--includeRecommended` a/nebo `--includeOptional`. Pro citlivější ovládací prvek, můžete připojit `;includeRecommended` nebo `;includeOptional` ID (například `--add Workload1;includeRecommended` nebo `--add Workload2;includeOptional`). Další informace najdete v tématu [pracovního vytížení a komponenta ID](workload-and-component-ids.md) stránky. <br/>**Poznámka:** Pokud `--add` se používá, pouze zadané úlohy a komponenty a jejich závislosti se stáhnou. Pokud `--add` neurčíte, všechny úlohy a komponenty se stáhnou do rozložení.|
| `--includeRecommended` | **Volitelné**: Obsahuje doporučené komponenty pro všechny úlohy, které jsou nainstalovány, ale nikoli volitelné komponenty. Úlohy jsou zadány buď pomocí `--allWorkloads` nebo `--add`. |
| `--includeOptional` | **Volitelné**: Obsahuje doporučené *a* volitelné komponenty pro všechny úlohy nebudou zahrnuty do rozložení. Úlohy jsou zadány s `--add`.  |
| `--keepLayoutVersion` | **Novinka v 15.3, volitelné**: Použijte změny na rozložení bez aktualizace verze rozložení. |
| `--verify` | **Novinka v 15.3, volitelné**: Ověřte obsah rozložení. Jsou uvedeny všechny soubory poškozen nebo chybí. |
| `--fix` | **Novinka v 15.3, volitelné**: Ověřte obsah rozložení.  Pokud nejsou nalezeny žádné soubory je poškozený nebo chybí, že jsou znovu staženy. Přístup k Internetu je potřeba opravit rozložení. |
| `--clean <one or more paths to catalogs>` | **Novinka v 15.3, volitelné**: Odstraní staré verze komponent z rozložení, který byl aktualizován na novější verzi. |

| **Možnosti rozšířené instalace** | **Popis** |
| ----------------------- | --------------- |
| `--channelId <id>` | **Volitelné**: ID kanálu pro instanci k instalaci. Toto je nezbytné instalační příkaz ignorován pro další příkazy `--installPath` je zadán. |
| `--channelUri <uri>` | **Volitelné**: Identifikátor URI manifest kanálu. V případě potřeby aktualizace nejsou `--channelUri` může odkazovat na neexistující soubor. (například--channelUri C:\doesntExist.chman) To je možné pro příkaz install; u ostatních příkazů se ignoruje. |
| `--installChannelUri <uri>` | **Volitelné**: Identifikátor URI manifest kanálu, který má použít pro instalaci. Určený identifikátor URI `--channelUri` (který musí být zadán při `--installChannelUri` určena) slouží ke zjištění aktualizací. To je možné pro příkaz install; u ostatních příkazů se ignoruje. |
| `--installCatalogUri <uri>` | **Volitelné**: Identifikátor URI manifestu katalogu použít k instalaci Je-li zadána, Správce kanálu se pokusí stáhnout manifest katalogu z tohoto identifikátoru URI před použitím tohoto identifikátoru URI v manifestu kanálu instalace. Tento parametr se používá pro podporu offline instalace, ve kterém se vytvoří mezipaměť rozložení s katalog produktů, které jsou staženy. To je možné pro příkaz install; u ostatních příkazů se ignoruje. |
| `--productId <id>` | **Volitelné** ID produktu pro instanci, která se nainstaluje. To je předem v běžných podmínek instalace. |
| `--wait` | **Volitelné**: Proces bude čekat, dokud nebude dokončena instalace před vrácením ukončovací kód. To je užitečné, když automatizace instalace, ve kterém musí jeden čekání na instalaci pro dokončení zpracování návratový kód od instalace. |
| `--locale <language-locale>` | **Volitelné**: Změňte jazyk zobrazení uživatelského rozhraní pro samotný instalační služby. Nastavení budou zachována. Další informace najdete v tématu [seznam národních prostředí jazyka](#list-of-language-locales) části na této stránce.|
| `--cache` | **Novinka v 15.2, volitelné**: Pokud jsou k dispozici, balíčky se uchovají po nainstalování pro další opravy. Tím se přepíše nastavení pro následné nainstaluje, opraví nebo úpravy globální zásady. Výchozí zásada je do mezipaměti balíčků. To se ignoruje pro příkaz odinstalovat. Přečtěte si, jak k [zakázání nebo přesunutí mezipaměti balíčku](disable-or-move-the-package-cache.md) Další informace. |
| `--nocache` | **Novinka v 15.2, volitelné**: Pokud jsou k dispozici, balíčky se odstraní po se nainstalovat ani opravit. Že se znovu stáhnou pouze v případě potřeby a znovu po použití odstraněna. Tím se přepíše nastavení pro následné nainstaluje, opraví nebo úpravy globální zásady. Výchozí zásada je do mezipaměti balíčků. To se ignoruje pro příkaz odinstalovat. Přečtěte si, jak k [zakázání nebo přesunutí mezipaměti balíčku](disable-or-move-the-package-cache.md) Další informace. |
| `--noUpdateInstaller` | **Novinka v 15.2, volitelné**: Pokud jsou k dispozici, lze zabránit instalačnímu programu ze samotné aktualizace, pokud je zadán tichý. Instalační program příkaz selže a vrátí nenulový ukončovací kód, pokud noUpdateInstaller je zadána s quiet, když se vyžaduje se aktualizace instalačního programu. |
| `--noWeb` | **Novinka v 15.3, volitelné**: Pokud jsou k dispozici, instalační program sady Visual Studio používá soubory v adresáři rozložení instalace sady Visual Studio. Pokud se uživatel pokusí nainstalovat součásti, které nejsou v rozložení, instalace selže.  Další informace najdete v tématu [nasazení z instalace v síti](create-a-network-installation-of-visual-studio.md). <br/><br/> **Důležité**: Tento přepínač nezastaví instalace sady Visual Studio z vyhledávají se aktualizace. Další informace najdete v tématu [řízení aktualizací nasazení sady Visual Studio založené na síti](controlling-updates-to-visual-studio-deployments.md).|
| `--path <name>=<path>` | **Nové ve verzi 15.7 volitelné**: Slouží k určení vlastní instalační cesty pro instalaci. Podporované cesty, které jsou sdíleny názvy, mezipaměť a instalace. |
| `--path cache=<path>` | **Nové ve verzi 15.7 volitelné**: Používá umístění, které zadáte ke stažení instalačních souborů. Toto umístění lze nastavit pouze při prvním je nainstalována aplikace Visual Studio. Příklad: `--path cache="C:\VS\cache"` |
| `--path shared=<path>` | **Nové ve verzi 15.7 volitelné**: Obsahuje sdílené soubory pro instalaci sady Visual Studio vedle sebe. Některé nástroje a sady SDK nainstalovat do umístění na této jednotce, zatímco jiné můžou toto nastavení přepsat a nainstalovat na jinou jednotku. Příklad: `--path shared="C:\VS\shared"` <br><br>Důležité: To lze nastavit pouze jednou a na prvním je nainstalována aplikace Visual Studio. |
| `--path install=<path>` | **Nové ve verzi 15.7 volitelné**: Ekvivalentní `–-installPath`. Konkrétně `--installPath "C:\VS"` a `--path install="C:\VS"` jsou ekvivalentní. Pouze jeden z nich je možné najednou. |

## <a name="list-of-workload-ids-and-component-ids"></a>Seznam ID pracovního vytížení a komponenta ID

Seznam pracovního vytížení a komponenta ID seřazené podle produktu Visual Studio, najdete v článku [ID pracovního vytížení a komponenta Visual Studio](workload-and-component-ids.md) stránky.

## <a name="list-of-language-locales"></a>Seznam národních prostředí jazyka

| **Jazyk národního prostředí** | **Jazyk** |
| ----------------------- | --------------- |
| Cs-cz | Čeština |
| De-de | Němčina |
| En-us | Angličtina |
| ES-es | Španělština |
| Fr-fr | Francouzština |
| IT-it | Italština |
| Ja-jp | Japonština |
| Ko-kr | Korejština |
| PL-pl | Polština |
| pt-br | Portugalština – Brazílie |
| Ru-ru | Ruština |
| TR-tr | Turečtina |
| Zh-cn | Čínština (zjednodušená) |
| Zh-tw | Čínština (tradiční) |

## <a name="error-codes"></a>Kódy chyb

V závislosti na výsledek operace `%ERRORLEVEL%` proměnnou prostředí je nastavená na jednu z následujících hodnot:

| **Hodnota** | **výsledek** |
| --------- | ---------- |
| 0 | Operace byla úspěšně dokončena |
| 1602 | Operace byla zrušena |
| 3010 | Operace byla úspěšně dokončena, ale instalace aktualizace vyžaduje restartování, než je možné |
| 5004 | Operace byla zrušena |
| 5007 | Operace byla blokována – počítač nesplňuje požadavky |
| Ostatní | Došlo k selhání podmínku – Další informace v protokolech |

Každá operace vygeneruje několik souborů protokolu v `%TEMP%` adresáře, které označují průběh instalace. Řadit podle data složce a vyhledat soubory, které začínají `dd_bootstrapper`, `dd_client`, a `dd_setup` pro zaváděcí nástroj, instalační program aplikace a nastavení modulu, v uvedeném pořadí.

[!INCLUDE[install_get_support_md](includes/install_get_support_md.md)]

## <a name="see-also"></a>Viz také:

- [Příklady parametrů příkazového řádku pro instalaci sady Visual Studio](command-line-parameter-examples.md)
- [Vytvoření offline instalace sady Visual Studio](create-an-offline-installation-of-visual-studio.md)
- [Automatizace instalace sady Visual Studio souborem odpovědí](automated-installation-with-response-file.md)
- [ID úloh a komponent sady Visual Studio](workload-and-component-ids.md)

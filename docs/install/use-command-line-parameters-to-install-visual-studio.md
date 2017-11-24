---
title: "Používání parametrů příkazového řádku pro instalaci sady Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 09/22/2017
ms.reviewer: tims
ms.suite: 
ms.technology: vs-acquisition
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- command-line parameters
- switches
- command prompt
ms.assetid: 480f3cb4-d873-434e-a8bf-82cff7401cf2
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.openlocfilehash: ff653e6fd9fb33cd7141671e9b77f297f8457a8b
ms.sourcegitcommit: eb954434c34b4df6fd2264266381b23ce9e6204a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/22/2017
---
# <a name="use-command-line-parameters-to-install-visual-studio-2017"></a>Nainstalujte Visual Studio 2017 pomocí parametrů příkazového řádku
Když instalujete Visual Studio 2017 z příkazového řádku, můžete řídit nebo upravit instalaci různých parametry příkazového řádku. Z příkazového řádku můžete provádět následující akce:

- Spusťte instalaci pomocí určitých možností předem vybrali.
- Automatizovat proces instalace.
- Vytvoření mezipaměti (rozložení) instalačních souborů pro pozdější použití.

Možnosti příkazového řádku se používají ve spojení s zaváděcí nástroj instalační program, který je soubor malá (přibližně 1MB), který zahájí proces stahování. Zavaděč je první spustitelný soubor, který se spustí, když si stáhnout z webu sady Visual Studio. Chcete-li získat přímý odkaz na nejnovější verzi bootstrapper pro edici produktu, který instalujete pomocí následujících odkazů:

* [Visual Studio 2017 Enterprise](https://aka.ms/vs/15/release/vs_enterprise.exe)
* [Visual Studio 2017 Professional](https://aka.ms/vs/15/release/vs_professional.exe)
* [Visual Studio 2017 Community](https://aka.ms/vs/15/release/vs_community.exe)

## <a name="list-of-command-line-parameters"></a>Seznam parametrů příkazového řádku  
 Parametry příkazového řádku Visual Studio jsou velká a malá písmena.

> Syntaxe:`vs_enterprise.exe [command] <options>...`

(Nahraďte `vs_enterprise.exe` podle potřeby pro edici produktu instalujete. Příklady najdete v tématu [příklady parametr příkazového řádku](command-line-parameter-examples.md) stránky.)

| **Příkaz** | **Popis** |
| ----------------------- | --------------- |
| (prázdný) | Nainstaluje produkt. |
| `modify` | Upravuje nainstalovaný produkt. |
| `update` | Aktualizuje nainstalovaný produkt. |
| `repair` | Opraví nainstalovaný produkt. |
| `uninstall` | Odinstaluje nainstalovaný produkt. |

| **Možnost instalace** | **Popis** |
| ----------------------- | --------------- |
| `--installPath <dir>` | Instalační adresář pro instanci k provedení akce. Pro příkaz instalace jde **volitelné** a nainstalovanou instanci. Pro jiné příkazy jde **požadované** a nainstalovanou dříve nainstalovanou instanci. |
| `--addProductLang <language-locale>` | **Volitelné**: během instalace nebo upravte činnost, tato hodnota určuje jazykové sady uživatelského rozhraní, které jsou nainstalovány do produktu. Může se objevit vícekrát na příkazový řádek pro přidání více jazykových sad. Pokud není přítomný, instalace používá národní prostředí počítače. Další informace najdete v tématu [seznam národní prostředí](#list-of-language-locales) části na této stránce.|
| `--removeProductLang <language-locale>` | **Volitelné**: během instalace nebo upravte činnost, tato hodnota určuje jazykové sady uživatelského rozhraní, které budou odebrány z produktu. Může se objevit vícekrát na příkazový řádek pro přidání více jazykových sad. Další informace najdete v tématu [seznam národní prostředí](#list-of-language-locales) části na této stránce.|
| `--add <one or more workload or component IDs>` | **Volitelné**: jeden nebo více úloh nebo ID součástí, které chcete přidat. Artefaktu požadované součásti jsou nainstalovány, ale ne doporučené nebo volitelné součásti. Můžete řídit další součásti globálně pomocí `--includeRecommended` nebo `--includeOptional`. Pro řízení citlivější, můžete připojit `;includeRecommended` nebo `;includeOptional` ID (například `--add Workload1;includeRecommended` nebo `--add Workload2;includeRecommended;includeOptional`). Další informace najdete v tématu naše [zatížení a ID součástí](workload-and-component-ids.md) stránky. Tato možnost v případě potřeby můžete opakovat.|
| `--remove <one or more workload or component IDs>` | **Volitelné**: jeden nebo více úloh nebo ID součástí odebrat. Další informace najdete v tématu naše [zatížení a ID součástí](workload-and-component-ids.md) stránky. Tato možnost v případě potřeby můžete opakovat.|
| `--in <path>` | **Volitelné**: URI nebo cestu k souboru odpovědí.  |
| `--all` | **Volitelné**: jestli se mají nainstalovat všechny úlohy a součásti pro produkt. |
| `--allWorkloads` | **Volitelné**: nainstaluje všechny úlohy a součásti žádné doporučené nebo volitelné součásti. |
| `--includeRecommended` | **Volitelné**: obsahuje doporučené součásti pro všechny úlohy, které jsou nainstalovány, ale nikoli volitelné součásti. Úlohy jsou zadány buď pomocí `--allWorkloads` nebo `--add`. |
| `--includeOptional` | **Volitelné**: obsahuje volitelné součásti pro všechny úlohy, které jsou nainstalovány, ale ne doporučené součásti. Úlohy jsou zadány buď pomocí `--allWorkloads` nebo `--add`.  |
| `--quiet, -q` | **Volitelné**: nezobrazí žádné uživatelské rozhraní během instalace. |
| `--passive, -p` | **Volitelné**: Zobrazit uživatelské rozhraní, ale není vyžádání zásahu od uživatele. |
| `--norestart` | **Volitelné**: Pokud existuje, příkazy pomocí `--passive` nebo `--quiet` nebude automaticky restartuje počítač (v případě potřeby).  To je ignorována, pokud ani `--passive` ani `--quiet` nejsou zadány.  |
| `--nickname <name>` | **Volitelné**: definuje Přezdívka přiřadit nainstalovaný produkt. Přezdívka nesmí být delší než 10 znaků.  |
| `--productKey` | **Volitelné**: definuje kód product key pro nainstalovaný produkt. Skládá se z 25 alfanumerických znaků, buď ve formátu `xxxxx-xxxxx-xxxxx-xxxxx-xxxxx` nebo `xxxxxxxxxxxxxxxxxxxxxxxxx`. |
| `--help, --?, -h, -?` | Zobrazte offline verzi této stránky. |

> Poznámka: Při zadávání více úloh a součásti, je nutné zopakovat `--add` nebo `--remove` přepínač příkazového řádku pro každou položku.

| **Možnosti rozložení** | **Popis** |
| ----------------------- | --------------- |
| `--layout <dir>` | Určuje adresář, který chcete vytvořit offline instalovat mezipaměti. Další informace najdete v tématu [vytvořit síťovou instalaci sady Visual Studio](create-a-network-installation-of-visual-studio.md).|
| `--lang <one or more language-locales>` | **Volitelné**: použít s `--layout` Příprava offline nainstalovat mezipaměti s balíčků prostředků s zadaný jazyk(y). Další informace najdete v tématu [seznam národní prostředí](#list-of-language-locales) části na této stránce.|
| `--add <one or more workload or component IDs>` | **Volitelné**: jeden nebo více úloh nebo ID součástí, které chcete přidat. Artefaktu požadované součásti jsou nainstalovány, ale ne doporučené nebo volitelné součásti. Můžete řídit další součásti globálně pomocí `--includeRecommended` nebo `--includeOptional`. Pro řízení citlivější, můžete připojit `;includeRecommended` nebo `;includeOptional` ID (například `--add Workload1;includeRecommended` nebo `--add Workload2;includeOptional`). Další informace najdete v tématu naše [zatížení a ID součástí](workload-and-component-ids.md) stránky. <br/>**Poznámka:**: Pokud `--add` je použít, pouze zadané úlohy a součásti a jejich závislosti se stáhnou. Pokud `--add` není zadán, všechny úlohy a součásti se stáhnou do rozložení.|
| `--includeRecommended` | **Volitelné**: obsahuje doporučené součásti pro všechny úlohy, které jsou nainstalovány, ale nikoli volitelné součásti. Úlohy jsou zadány buď pomocí `--allWorkloads` nebo `--add`. |
| `--includeOptional` | **Volitelné**: obsahuje doporučené *a* volitelné součásti pro všechny úlohy, nebudou zahrnuty do rozložení. Úlohy zadávají s `--add`.  |
| `--keepLayoutVersion` | **Novinka v 15.3, volitelné**: použít změny v rozložení bez aktualizace verze rozložení. |
| `--verify` | **Novinka v 15.3, volitelné**: Ověřte obsah rozložení.  Jsou uvedeny všechny soubory poškozeno nebo chybí. |
| `--fix` | **Novinka v 15.3, volitelné**: Ověřte obsah rozložení.  Pokud se zjistí, že všechny soubory poškozený nebo chybí, jsou znovu načtena.  Přístup k Internetu je potřeba opravit rozložení. |
| `--clean <one or more paths to catalogs>` | **Novinka v 15.3, volitelné**: Odebere staré verze součástí z rozložení, který byl aktualizován na novější verzi. |

| **Instalace rozšířené možnosti** | **Popis** |
| ----------------------- | --------------- |
| `--channelId <id>` | **Volitelné**: ID kanálu pro instanci k instalaci. To je potřeba pro příkaz instalace, pokud ignorována pro jiné příkazy `--installPath` je zadán. |
| `--channelUri <uri>` | **Volitelné**: identifikátoru URI manifestu kanálu. V případě potřeby aktualizace nejsou `--channelUri` může ukazovat na neexistující soubor. (například – channelUri C:\doesntExist.chman) To lze použít pro instalační příkaz; je ignorován u ostatních příkazů. |
| `--installChannelUri <uri>` | **Volitelné**: identifikátoru URI manifestu kanál sloužící k instalaci. Identifikátor URI určeného `--channelUri` (která musí být zadán při `--installChannelUri` je zadána) se používá pro zjišťování aktualizací. To lze použít pro instalační příkaz; je ignorován u ostatních příkazů. |
| `--installCatalogUri <uri>` | **Volitelné**: identifikátoru URI manifestu katalogu pro instalaci. -Li zadána, správce kanál pokusí stáhnout manifest katalogu z tento identifikátor URI před použitím identifikátoru URI v manifestu kanál instalace. Tento parametr se používá pro podporu offline instalace, které se vytvoří mezipaměť rozložení s katalog produktů, které jsou staženy. To lze použít pro instalační příkaz; je ignorován u ostatních příkazů. |
| `--productId <id>` | **Volitelné** ID produktu pro instanci, kterou bude nainstalována. To je předem v běžných podmínek instalace. |
| `--wait` | **Volitelné**: proces budou čekat na dokončení instalace před vrácením ukončovací kód. To je užitečné v případě automatizace instalace, kde jeden musí počkat pro instalaci na dokončení zpracování návratový kód od instalace. |
| `--locale <language-locale>` | **Volitelné**: změnit jazyk zobrazení uživatelského rozhraní pro instalační program sám sebe. Nastavení bude natrvalo. Další informace najdete v tématu [seznam národní prostředí](#list-of-language-locales) části na této stránce.|
| `--cache` | **Novinka v 15.2 volitelné**: Pokud existuje, balíčky se zachová po nainstalování pro následné opravy. Přepíše nastavení má být použit pro následné nainstaluje, opraví nebo úpravy globální zásady. Výchozí zásada je do mezipaměti balíčků. To je pro příkaz odinstalace ignorovat. Najdete v návodu k [zakázat nebo přesunout do mezipaměti balíček](disable-or-move-the-package-cache.md) Další informace. |
| `--nocache` | **Novinka v 15.2 volitelné**: Pokud existuje, balíčky se odstraní poté, co byla nainstalována nebo opravit. Budou se znovu stáhnou jenom v případě potřeby a znovu za použití odstraní. Přepíše nastavení má být použit pro následné nainstaluje, opraví nebo úpravy globální zásady. Výchozí zásada je do mezipaměti balíčků. To je pro příkaz odinstalace ignorovat. Najdete v návodu k [zakázat nebo přesunout do mezipaměti balíček](disable-or-move-the-package-cache.md) Další informace. |
| `--noUpdateInstaller` | **Novinka v 15.2 volitelné**: Pokud existuje, brání instalačnímu programu aktualizace samotné, pokud je zadán tichý. Instalační program se nezdaří příkazu a vrátí nenulový ukončovací kód, pokud noUpdateInstaller je definován s Tichý, když je nutná aktualizace Instalační služby. |
| `--noWeb` | **Novinka v 15.3, volitelné**: Instalační program nyní stáhnout veškerý obsah, který je instalace z Internetu.  Veškerý obsah, který se instaluje musí být k dispozici v offline rozložení.  Pokud rozložení chybí obsah, instalace se nezdaří.  Další informace najdete v tématu [nasazení z síťovou instalaci](create-a-network-installation-of-visual-studio.md). |

## <a name="list-of-workload-ids-and-component-ids"></a>Seznam ID úlohy a ID součástí
Seznam úloh a ID součástí, které jsou seřazené podle produktu Visual Studio, najdete v článku [zatížení 2017 Visual Studio a ID součástí](workload-and-component-ids.md) stránky.

## <a name="list-of-language-locales"></a>Seznam národní prostředí
| **Národní prostředí** | **Jazyk** |
| ----------------------- | --------------- |
| cs-CZ | Čeština |
| de-DE | Němčina |
| en US | Angličtina |
| ES-ES | Španělština |
| fr-FR | Francouzština |
| IT-IT | Italština |
| ja-JP | Japonština |
| ko-KR | Korejština |
| pl-PL | Polština |
| pt-BR | Portugalština – Brazílie |
| ru-RU | Ruština |
| tr-TR | Turečtina |
| zh-CN | -Čínština, zjednodušená čínština |
| zh-TW. | Tradiční čínština – |

## <a name="error-codes"></a>Kódy chyb
V závislosti na výsledku operace `%ERRORLEVEL%` proměnné prostředí se nastaví na jednu z následujících hodnot:

| **Hodnota** | **Výsledek** |
| --------- | ---------- |
| 0 | Operace byla úspěšně dokončena |
| 1602 | Operace byla zrušena |
| 3010 | Operace úspěšně dokončena, ale instalace vyžaduje restart, před použitím |
| 5004 | Operace byla zrušena |
| 5007 | Operace byla blokována – počítač nesplňuje požadavky |
| Ostatní | Došlo k selhání podmínku – Zkontrolujte protokoly pro další informace |

Generuje několik souborů protokolu v každé operace `%TEMP%` adresář, který informace o průběhu instalace. Řazení podle data složce a hledat soubory, které začínají `dd_bootstrapper`, `dd_client`, a `dd_setup` pro zavaděč, instalační program aplikace a potom instalaci modul, v uvedeném pořadí.

## <a name="get-support"></a>Získat podporu
V některých případech může problémů. Pokud se nezdaří instalace Visual Studia, najdete v článku [problémy instalace a upgrade řešení potíží s Visual Studio 2017](troubleshooting-installation-issues.md) stránky. Pokud se žádný z kroků pro řešení potíží, kontaktujte nás pomocí živé konverzace pro pomoc s instalací (pouze v angličtině). Podrobnosti najdete v tématu [stránky podpory sady Visual Studio](https://www.visualstudio.com/vs/support/#talktous).

Tady je několik další možnosti podpory:
* Můžete hlášení problémů produktu pro nás prostřednictvím [nahlásit problém](../ide/how-to-report-a-problem-with-visual-studio-2017.md) nástroj, který se zobrazí v instalačním programu Visual Studio i v integrovaném vývojovém prostředí sady Visual Studio.
* Návrh produktu s námi můžete sdílet na [UserVoice](https://visualstudio.uservoice.com/forums/121579).
* Můžete sledovat problémy produktu v [Visual Studio Community vývojáře](https://developercommunity.visualstudio.com/)a klást otázky a odpovědi.
* Můžete také použít s námi a jinými vývojáři Visual Studio prostřednictvím našich [Visual Studio konverzace v komunitě Gitter](https://gitter.im/Microsoft/VisualStudio).  (Tato možnost vyžaduje [Githubu](https://github.com/) účtu).

## <a name="see-also"></a>Viz také

 * [Nainstalovat Visual Studio 2017](install-visual-studio.md)
 * [Vytvoření offline instalace Visual Studio 2017](create-an-offline-installation-of-visual-studio.md)
 * [Příklady parametr příkazového řádku pro instalaci Visual Studio 2017](command-line-parameter-examples.md)
 * [Automatizovat instalaci sady Visual Studio se souborem odpovědí](automated-installation-with-response-file.md)

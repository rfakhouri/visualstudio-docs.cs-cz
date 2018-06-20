---
title: Pracovní prostory R
description: Tom, jak řídit, kde běží kód R pomocí pracovní prostory v sadě Visual Studio.
ms.date: 01/24/2018
ms.prod: visual-studio-dev15
ms.technology: vs-rtvs
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- data-science
ms.openlocfilehash: 859e44c912ed98a50d5127675eb2c1bed699ede6
ms.sourcegitcommit: f685fa5e2df9dc307bf1230dd9dc3288aaa408b5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/19/2018
ms.locfileid: "36238324"
---
# <a name="control-where-r-code-runs-with-workspaces"></a>Ovládací prvek, kde běží kód R s nimi

Pracovního prostoru v R nástrojů pro Visual Studio (RTVS) umožňuje nakonfigurovat, kde R běží relace, který se může stát při místních i vzdálených počítačů. Cílem je umožnit práci na buď pomocí porovnatelný z hlediska uživatelské prostředí, které vám dává možnost využívat výhod potenciálně výkonnější počítače založené na cloudu.

Otevřete **pracovních prostorů** okna, použijte **R nástroje** > **Windows** > **pracovních prostorů** příkaz nebo klikněte na tlačítko **Ctrl**+**9**.

![Okno pracovní prostory v R Tools pro Visual Studio (VS2017)](media/workspaces-window.png)

V tomto okně na zelenou značku zaškrtnutí označuje active pracovního prostoru, ke kterému je vázán RTVS. Výběr modrou šipkou nastaví active pracovního prostoru. Na ikonu nastavení (ozubené kolečko) vedle každém pracovním prostoru můžete změnit její název, umístění a argumenty příkazového řádku. Červené X odebere ručně přidaná pracovního prostoru.

## <a name="save-and-reset-a-workspace"></a>Uložte a resetovat pracovního prostoru

Ve výchozím nastavení není RTVS uložit stav pracovního prostoru, když zavřete a znovu otevřít projekt. Můžete změnit toto chování však prostřednictvím [možnosti pracovního prostoru](options-for-r-tools-in-visual-studio.md#workspace).

**R nástroje** > **relace** > **resetovat** příkaz a na panelu nástrojů tlačítko Obnovit v okně interaktivní také obnovit stav pracovního prostoru na kterémkoli čas. S vzdálené pracovní prostory odstraní resetování uživatelský profil vytvořen při prvním připojení ke vzdálenému serveru, které efektivně odstraní všechny soubory, které se shromáždily existuje.

## <a name="local-workspaces"></a>Místní pracovní prostory

Zobrazí se seznam místní pracovní prostory všechny překladače R, které jste nainstalovali ve vašem počítači. 

Při spuštění sady Visual Studio se pokusí automaticky zjistit všechny verze R, který jste nainstalovali tak, že vyhledá **HKEY_LOCAL_MACHINE\Software\R základní\**  klíč registru. Protože tato kontrola se provádí pouze při spuštění, musíte restartovat Visual Studio, pokud instalujete nový R překladač.

RTVS nemusí rozpoznat překladač R, který je nainstalován v nestandardním způsobem (například při jednoduše kopírování souborů do složky namísto spuštění Instalační program). V takovém případě ručně vytvořte nový pracovní prostor místní R takto:

1. Vyberte **přidat** tlačítka v okně pracovních prostorů.
1. Zadejte název pro nový pracovní prostor.
1. Zadejte cestu ke kořenové složce R, což je ten, který obsahuje *bin* složku s překladač, společně s všechny volitelné argumenty příkazového řádku mají být předány překladač při RTVS spuštění systému.
1. Vyberte **Uložit** po dokončení.

![Přidání nový pracovní prostor](media/workspaces-add-new.png)

## <a name="remote-workspaces"></a>Vzdálené pracovní prostory

Vzdálené pracovní prostory umožňují připojit se k relaci R ve vzdáleném počítači. (Viz [nastavení vzdálené pracovní prostory](setting-up-remote-r-workspaces.md) pro postup konfigurace počítače pro tento účel.)

Visual Studio nerozpozná automaticky vzdálené pracovní prostory, takže je třeba je ručně pomocí přidat **přidat** tlačítka v okně pracovní prostory, jak je popsáno v předchozí části. V takovém případě zadejte identifikátor URI vzdáleného počítače, nikoli místní cestu.

> [!Important]
> Vzdálené pracovní prostory se identifikují podle identifikátoru URI, *musí používat protokol HTTPS* zajistit soukromí a integritu komunikace se vzdáleným počítačem. Visual Studio se nemůže připojit ke vzdálenému počítači, který nepodporuje protokol HTTPS.

> [!Note]
> Vzdálené pracovní prostory jsou efektivně ve verzi preview. Práce na lepší provádění problém synchronizace souboru pro budoucí verze jsme Vítejte nápady a zpětné vazby.

## <a name="remote-workspace-logon"></a>Pracovní prostor vzdálené přihlášení

Musíte použít uživatelské jméno a heslo k přihlášení do vzdáleného pracovního prostoru.

### <a name="logon-to-windows-workspace"></a>Přihlášení do pracovního prostoru Windows

Pokud je vzdálený počítač pomocí účtu domény instalačního programu, můžete pro přístup k vzdálené pracovního prostoru přihlášení do domény. Pokud není, pak budete muset použít `machine-name\username` formátu přihlašování pomocí účtu počítače ve vzdáleném počítači.

### <a name="logon-to-linux-workspace"></a>Přihlášení do pracovního prostoru Linux

Pro přihlašování pomocí účtu linux `<<unix>>\username` formátu. Například, pokud máte účet s názvem `ruser`, pak byste měli zadat uživatelské jméno jako `<<unix>>\ruser`.

## <a name="switch-between-workspaces"></a>Přepínání mezi pracovních prostorů

RTVS je najednou vázaný jenom do jednoho pracovního prostoru. Vázané pracovního prostoru je indikován malé zeleného zaškrtnutí v okně pracovních prostorů. Ve výchozím nastavení RTVS sváže poslední otevřít místní pracovní prostor v předchozí relaci.

Chcete-li změnit active pracovního prostoru, vyberte modrou šipkou požadovaný pracovní prostor. Díky tomu vás vyzve k uložení relace, ukončí aktuální pracovní prostor a potom se přepne do nového.

> [!Tip]
> Zakázat uložení výzvy, vyberte **R nástroje** > **možnosti** příkazů a nastavte **zobrazit dialogové okno potvrzení před často používaných** možnost `No`. V tématu [možnosti pracovního prostoru](options-for-r-tools-in-visual-studio.md#workspace).

Pokud se pokusíte přepnout do místní pracovní prostor, který odinstalovat, nebo do vzdáleného pracovního prostoru, který není k dispozici, RTVS nemusí být vázána na jakémkoliv pracovním prostoru. Při zadávání kódu v okně interaktivní nebo se pokuste spustit kód jinak v důsledku toho může zobrazit chyba:

![Chyba při žádné pracovní prostor je vázán k RTVS](media/workspaces-disconnected-interactive-window.png)

Chcete-li vyřešit tento problém, přepněte na jiného pracovního prostoru v okně pracovních prostorů. Pokud jsou k dispozici žádné pracovní prostory, budete muset nainstalovat R překladač. Můžete také zkusit spustit sadu Visual Studio, pokud jste nainstalovali překladač při spuštění sady Visual Studio.

### <a name="switch-to-a-remote-workspace"></a>Přepnout na vzdálené pracovní prostor

RTVS vás vyzve k zadání přihlašovacích údajů při prvním připojení do vzdáleného pracovního prostoru, pak ukládá do mezipaměti tyto přihlašovací údaje (pomocí zabezpečené schránku na pověření systému Windows) na novější relací. Komunikace se vzdáleným serverem se pak provádí bezpečně přes protokol HTTPS (což je vyžadováno).

V závislosti na konfiguraci serveru může se zobrazit upozornění při připojování čtení, certifikát "certifikát zabezpečení předložený vzdálené R neumožňuje nám prokázat, že jste skutečně připojení k počítači (název)."

![Certifikát podepsaný svým držitelem upozornění při připojování ke vzdálené pracovní prostor](media/workspaces-remote-self-signed-certificate-warning.png)

Certifikát je RTVS předloží počítači, který se pokoušíte připojit k dokumentu. Certifikát obsahuje pole, které identifikují identifikátor URI tohoto počítače. Toto upozornění se zobrazí, když zjistí RTVS neshodu mezi identifikátor URI v certifikátu a identifikátor URI používaný pro připojení k počítači, která určuje, že zabezpečení serveru ohrožený.

Ale toto upozornění se zobrazí také pokud *certifikát podepsaný svým držitelem* byla použita k povolit protokol HTTPS na vzdáleném počítači místo pomocí jedné z důvěryhodného zprostředkovatele. Další informace najdete v tématu [nastavení vzdálené pracovní prostory](setting-up-remote-r-workspaces.md).

## <a name="directories-on-local-and-remote-computers"></a>Adresáře na místních i vzdálených počítačů

Ve výchozím nastavení, když spustíte nové interpretační R v místní pracovní prostor, je aktuální pracovní adresář *%userprofile%\Documents*. Můžete změnit adresář v současně pomocí **R nástroje** > **pracovní adresář** příkazy, nebo pomocí kliknete pravým tlačítkem na projekt v Průzkumníku řešení Visual Studio a vyberete příkazy, jako je  **Nastavit pracovní adresář tady**.

Když poprvé připojíte ke vzdálenému počítači, RTVS automaticky vytvoří profil uživatele podle přihlašovacích údajů, který nastaví pracovní adresář *dokumenty* ve složce Tento profil. Tato složka se použije pro všechny následné vzdálené relace, které používají stejné přihlašovací údaje.

V důsledku toho je přesné umístění, kde běží váš kód se může lišit mezi místní a vzdálené pracovní prostory. V kódu pak vždy používejte relativní cesty a datové soubory, tak, aby váš kód je přenosné napříč pracovních prostorů.

Všimněte si také, že se vzdálené pracovní prostory, všechny soubory v pracovním adresáři zůstávají na svém místě napříč relacemi pro stejný profil uživatele. Jak již bylo uvedeno dříve, můžete odstranit tyto soubory pomocí **R nástroje** > **relace** > **resetovat** příkaz (nebo na tlačítko Obnovit v interaktivní okno) při použití vzdáleného pracovního prostoru. Tento příkaz znovu odstraní profil uživatele ze serveru, který se znovu vytvoří při opětovném připojení.

## <a name="copy-project-files-to-remote-workspaces"></a>Zkopírujte soubory projektu do vzdálené pracovní prostory

Při práci s R projekty v sadě Visual Studio, místní počítač má nejnovější soubory projektu vždy i když používáte vzdálené pracovního prostoru. To znamená při otevření projektu v sadě Visual Studio (což obvykle znamená, otevřete řešení obsahující tento projekt), RTVS předpokládá, že obsah projektu zcela nacházet v místním počítači. Vzdálené pracovní prostor je ve skutečnosti jenom dočasné hostiteli pro soubory projektu a všechny výstup z kódu. To znamená, například, že při načítání souboru pomocí `source` v okně interaktivní musí tento soubor už být na vzdáleném počítači v cestě zadáte, nebo musí být v aktuální pracovní adresář překladač vzdálené R (nastavit `setwd()`</c2>funkce).

Soubory se zkopírují na vzdálený server následujícím způsobem:

- Práce se soubory vzdáleně pomocí interaktivních okna, je nutné nejprve zkopírovat je ručně kliknutím pravým tlačítkem myši na tyto soubory (nebo projekt) v Průzkumníku řešení a výběrem **vybrán zdroj**. U jednotlivých souborů zkopírují se do pracovního adresáře na serveru. Při kopírování projektu, RTVS vytvoří složku pro projekt.

- Můžete také zkopírovat soubory pak výběrem v Průzkumníku řešení a potom vyberete **zdrojové vybrané soubory (s)**. Tato akce je načte do okna interaktivní a něm běží. Pokud relace je připojený ke vzdálenému počítači, soubory se zkopírují existuje nejdřív.

- Když RTVS je vázán k vzdáleného prostoru a stisknete **F5**, vyberte **ladění** > **spustit ladění**, nebo v opačném případě začněte spuštěním kódu, RTVS ve výchozím nastavení zkopíruje soubor projektu do vzdáleného pracovního prostoru automaticky (jak za účelem řízení najdete níže).

- Všechny soubory, které již existují na serveru se přepíší.

> [!Note]
> Protože RTVS nelze intercept spolehlivě všechna volání funkce R, volání funkcí, jako `source()` nebo `runApp()` (pro lesklý aplikace) v rámci okna interaktivní nemá *není* zkopírujte soubory do vzdáleného pracovního prostoru.

[Vlastnosti projektu](r-projects-in-visual-studio.md#project-properties) řízení zda RTVS zkopíruje soubory, když na projekt je spustit a přesně, které soubory budou zkopírovány. Otevřete tuto stránku, vyberte **projektu** > **vlastnosti (název)** příkazu nabídky, nebo klikněte pravým tlačítkem na projekt v Průzkumníku řešení a vyberte **vlastnosti**.

![Vlastnosti projektu karta s přenos souborů parametry spuštění](media/workspaces-remote-file-transfer-filter-settings.png)

Zde **přenos souborů při spuštění** vlastnost určuje, zda RTVS automaticky zkopíruje soubory projektu. **Souborů k přenosu** hodnotu pak přesně které soubory se přenášejí filtry. Ve výchozím nastavení se zkopírovat jenom *. R*, *. RMD*, *.sql*, *.md*, a *sada* soubory. Toto chování se vyhnete nechtěně kopírování velkých objemů dat souborů na server s každé spuštění. 

## <a name="copy-files-from-a-remote-workspace"></a>Kopírování souborů ze vzdáleného pracovního prostoru

Pokud váš skript jazyka R generuje soubory na serveru, můžete zkopírovat tyto soubory zpět do klienta pomocí `rtvs::fetch_file` funkce. Tato funkce přijímá v minimálně vzdálené cestu k souboru, který chcete zkopírovat do počítače a volitelně cílová cesta ve vašem počítači. Pokud nezadáte cestu, bude soubor zkopírován do vašeho *%userprofile%\Downloads* složky.

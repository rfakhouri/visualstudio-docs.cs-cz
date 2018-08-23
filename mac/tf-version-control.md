---
title: Správa verzí TF
description: Připojení k serveru Team Foundation Server nebo Visual Studio Team Services s Team Foundation – správa verzí.
author: conceptdev
ms.author: crdun
ms.date: 05/03/2018
ms.topic: article
ms.technology: vs-ide-general
ms.assetid: 52D3D26A-4D01-4FD1-AAA1-AE7D7BD39746
ms.openlocfilehash: 101f002f6c311fe5aaefa78c246602fd45514603
ms.sourcegitcommit: 2597236a481afbaf1ad4915743898ee1aee49760
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/10/2018
ms.locfileid: "42624153"
---
# <a name="connecting-to-team-foundation-version-control"></a>Připojování k Team Foundation – správa verzí 

> [!NOTE]
> **Poznámka:**: podpora správy verzí Team Foundation je aktuálně ve verzi preview a některé funkce není dosud plně funkční. Jsme rádi, zpětnou vazbu od vás na všechny problémy na [komunity vývojářů](https://developercommunity.visualstudio.com/spaces/41/index.html). Další změny jsou stále chystá!

Visual Studio Team Services (VSTS) a Team Foundation Server (TFS) poskytuje dva modely správy verzí: Git, který je distribuován správy verzí a Team Foundation verze ovládacího prvku (TFVC), což je centralizovaná správa verzí. Tento článek obsahuje přehled a výchozí bod pro Team Foundation – správa verzí pomocí sady Visual Studio pro Mac.

## <a name="requirements"></a>Požadavky

* Visual Studio Community, Professional nebo Enterprise for Mac verze 7.5 nebo novější.
* Visual Studio Team Services nebo Team Foundation Server 2013 a novější.
* Projekt sady Visual Studio Team Services nebo Team Foundation Server nakonfigurován pro použití správy verzí Team Foundation.

## <a name="installation"></a>Instalace

V sadě Visual Studio pro Mac, zvolte **sady Visual Studio > rozšíření...**  z nabídky. V **Galerie** kartu, vyberte možnost **verzí > správy verzí Team Foundation serveru TFS a VSTS** a klikněte na tlačítko **instalace...** :

  ![Správce rozšíření](media/tfvc-install.png) 

Postupujte podle pokynů k instalaci rozšíření. Po instalaci ji restartujte integrované vývojové prostředí.

## <a name="updating-the-extension"></a>Aktualizuje se rozšíření

Aktualizace rozšíření TFVC probíhají pravidelně. Přístup k aktualizace, zvolte **sady Visual Studio > rozšíření...**  z nabídky a vybereme **aktualizace** kartu. Vyberte požadované rozšíření v seznamu a stisknutím klávesy **aktualizace** tlačítka:

  ![Aktualizace zobrazení Správce rozšíření](media/tfvc-update.png) 

Stisknutím klávesy **nainstalovat** v dalším dialogovém okně starý balíček odinstalovat a nainstalovat nové.

Informace o tom, co je nového v jednotlivých verzích, najdete v článku [poznámky k verzi](https://docs.microsoft.com/visualstudio/releasenotes/vs2017-mac-preview-relnotes#team-foundation-version-control-extension--release-notes).

## <a name="using-the-add-in"></a>Pomocí doplňku

Po instalaci rozšíření, vyberte **verzí > TFS/VSTS > Otevřít ze vzdáleného úložiště** položky nabídky. 

Zvolte buď Visual Studio Team Services nebo Team Foundation Server a začít pracovat se stisknutím klávesy **pokračovat**:

  ![Připojení k serveru](media/tfvc-choose-server-type.png)

### <a name="vsts-authentication"></a>Ověřování VSTS

Když vyberete projekt, který je hostovaný ve službě VSTS, budete vyzváni k zadání podrobnosti o vašem účtu Microsoft:

  ![Připojení k serveru VSTS](media/tfvc-vsts-login.png)

### <a name="tfs-authentication"></a>Ověřování serveru TFS

Pro připojení k TFS, zadejte podrobnosti o serveru a přihlašovací údaje účtu. Zadejte doménu na použití ověřování NTLM, jinak nechejte pole prázdné, použije se základní ověřování. Vyberte **přidat Server**: 

![Přihlaste se k serveru TFS](media/tfvc-login.png)

## <a name="selecting-a-project"></a>Výběr projektu

Jakmile byli jste úspěšně ověřeni, zobrazí se seznam úložišť, které jsou přidružené k účtu v **otevřít ze správy zdrojových kódů** dialogové okno:

  ![Otevřít ze správy zdrojových kódů dialogové okno s projekty, zobrazí](media/tfvc-vsts-projects.png)

Toto dialogové okno je uspořádaný s následující uzly:

- Účet VSTS nebo kolekci – zobrazí všechny účty připojené k účtu Microsoft, který jste přihlášení
- Týmové projekty – v rámci každé VSTS můžete mít několik týmových projektů. Týmový projekt, se hostuje zdrojový kód, pracovní položky a automatizované sestavování.

V tomto okamžiku můžete vyhledávat a filtrovat podle názvu projektu nebo účet.

### <a name="adding-a-new-server"></a>Přidání nového serveru

Chcete-li přidat nový server do seznamu, stiskněte **přidat hostitele** tlačítko **otevřít ze správy zdrojových kódů** dialogové okno:

![Zvýrazní tlačítko pro přidání nového serveru do seznamu přidat](media/tfvc-add-new-server.png)

Vyberte poskytovatele ze seznamu a zadejte svoje přihlašovací údaje:

![Dialogové okno zobrazující možnost pro poskytovatele správy zdrojového kódu](media/tfvc-add-new-creds.png)

## <a name="creating-a-new-workspace"></a>Vytváří se nový pracovní prostor

Pokud chcete začít pracovat s projektem, budete muset mít _pracovní prostor_. Pokud ještě nemáte pracovní prostor, můžete vytvořit jeden z **pracovní prostor** – pole se seznamem v **otevřít ze správy zdrojových kódů** dialogové okno:

![Vytvořit nový pracovní prostor – pole se seznamem možností](media/tfvc-create-new-workspace.png)

Nastavte název a místní cestu k novému pracovnímu prostoru a vyberte **vytvořit pracovní prostor**:

![Zadat místní cestu a název nového pracovního prostoru](media/tfvc-local-workspace.png)

## <a name="using-the-source-code-explorer"></a>Pomocí Průzkumníka zdrojového kódu

Po vytvoření pracovního prostoru a mapována do projektu, můžete začít pracovat s _Průzkumník zdrojového kódu_.

Otevřít Průzkumníka zdrojového kódu, vyberte **verzí > TFS/VSTS > Průzkumník správy zdrojového kódu**:

![Položka nabídky otevřete Průzkumníka zdrojového kódu](media/tfvc-source-control-explorer.png)

Průzkumník zdrojového kódu umožňuje procházet z namapované projekty, jejich soubory a složky. Také umožňuje provádět všechny akce správy základní zdrojů, jako:

- Získat nejnovější verzi
- Získání určité verze
- Rezervace souborů a vrácení souborů se změnami
- Zamknutí a odemknutí soubory
- Přidání, odstranění a přejmenování souborů
- Zobrazit historii
- Porovnejte změny.

Mnohé z těchto akcí jsou k dispozici prostřednictvím kontextu akce na projekt:

![Místní nabídka Akce pro projekt](media/tfvc-sourcecode-actions.png)

## <a name="managing-workspaces"></a>Správa pracovních prostorů

Pokud jste tak dosud neučinili vytvořit pracovní prostor, jak je popsáno v [vytvoření pracovního prostoru](#creating-a-new-workspace) oddílu, můžete si všimnout, že je prázdný Průzkumník zdrojového kódu:

![prázdný zdrojový kód explorer](media/tfvc-setup-empty-sce.png) 

Nastavení vzdáleného projekt pomocí místního pracovního prostoru, postupujte následovně:

1. Vyberte **Server** z pole se seznamem.
1. Mějte na paměti, že neexistují "žádné pracovní prostory" a zda je místní cesta "Nenamapované". Vyberte **nenamapované** odkazu zobrazíte **vytvořit nový pracovní prostor** dialogového okna.
1. Zadejte název pracovního prostoru a potom klikněte na tlačítko **pracovní složka** mapování projektu do místní složky v počítači:
    
    ![Vytvořit nový pracovní prostor dialog s informací, výchozí možnosti](media/tfvc-workspace1.png) 

1. Vyberte složky "$" do všech týmových projektů na serveru mapují na stejný pracovní prostor, nebo vyberte jednotlivé projekt a klikněte na tlačítko **OK**:
    
    ![Procházet pro složku dialogové okno zobrazující všechny projekty](media/tfvc-workspace2.png) 

1. Vyberte umístění na místním počítači, který chcete projekty do sady Management Pack a klikněte na tlačítko **vybrat složku**.
1. Zkontrolujte podrobnosti o nový pracovní prostor stisknutím kombinace kláves **OK**
    
    ![Vytvořit dialogové okno Nový pracovní prostor se přidá pracovní složky](media/tfvc-workspace3.png) 

Po nastavení pracovního prostoru lze změnit nebo odebrat po kliknutí **spravovat pracovní prostory** tlačítko v Průzkumníku zdrojového kódu.

![Správa pracovních prostorů](media/tfvc-workspace4.png)

## <a name="troubleshooting"></a>Poradce při potížích

### <a name="problems-using-basic-authentication"></a>Potíže při použití základního ověřování

Tyto možnosti lze použít k ověření serveru:

- OAuth
- Základní
- NTLM

Základní ověřování je nutná pro povolení **přihlašovací údaje pro alternativní ověření** ve VSTS, pomocí následujících kroků:

1. Přihlaste se jako vlastník účtu ke svému účtu VSTS (https://{youraccount}.visualstudio.com).
2. Z panelu nástrojů účtu, vyberte ikonu ozubeného kola a vyberte **zásady**:
    
    ![Vybraná možnost nastavení zásad](media/tfvc-auth2.png) 

3. Zkontrolujte nastavení připojení k aplikaci. Změna těchto nastavení v závislosti na vašich zásadách zabezpečení:
    
    ![Vybraná možnost nastavení zásad](media/tfvc-auth.png)  

### <a name="i-do-not-see-anything-in-tfvc"></a>Nevidím v TFVC nic

Nastavit si Team Foundation verze ovládacího prvku (TFVC) ve vašem vývojovém počítači můžete **musí** vytvořit pracovní prostor, jak je popsáno v [Správa pracovních prostorů](#managing-workspaces) oddílu.

V Průzkumníku správy zdrojového kódu, stiskněte **spravovat pracovní prostory** tlačítko. Postupujte podle kroků pro mapování týmového projektu do složky na svém vývojovém počítači.

### <a name="i-do-not-see-any--all-of-my-projects"></a>Nevidím žádné / all Moje projekty

Po ověření, měli byste vidět seznam projektů. Ve výchozím nastavení jsou uvedeny pouze projekty TFS do. Pokud chcete zobrazit jiné typy projektů, zaškrtněte políčko "«Zobrazit všechny projekty".

Mějte na paměti, že projekty, které jsou na serveru se nezobrazí, pokud nemáte dostatečná oprávnění.

#### <a name="i-am-getting-the-error-cannot-create-the-workspace-please-try-again"></a>Dochází k chybě "nejde vytvořit pracovní prostor. Zkuste to prosím znovu"

Při pokusu o [vytvořit nový pracovní prostor](#creating-a-new-workspace), se ujistěte, že jsou splněny následující podmínky:

- Zákaz použití neplatné znaky v názvu pracovního prostoru.
- Název musí být menší než 64 znaků.
- Místní cesta nemůže využívat ostatní pracovní prostory.
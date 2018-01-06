---
title: "Nasazování komponent COM s ClickOnce | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- registration-free COM deployment
- ClickOnce deployment, COM components
- COM components, deploying
- deploying applications [ClickOnce], COM components
- components, deploying
ms.assetid: 1a4c7f4c-7a41-45f2-9af4-8b1666469b89
caps.latest.revision: "12"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload: multiple
ms.openlocfilehash: a63073e86c3584253e67bf4d77f43006104de075
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="deploying-com-components-with-clickonce"></a>Nasazování komponent COM s ClickOnce
Nasazení komponent COM starší verze tradičně bylo snadné. Součásti musí být globálně registrované a to může způsobit nežádoucí vedlejší účinky mezi překrývající se aplikace. Tato situace se obecně nejedná o problém v aplikacích rozhraní .NET Framework protože součásti jsou naprosto izolované aplikace nebo jsou kompatibilní vedle sebe. Visual Studio umožňuje nasadit izolované komponenty modelu COM v systému Windows XP nebo novější operační systém.  
  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]poskytuje snadný a bezpečný mechanismus pro nasazení aplikací .NET. Ale pokud aplikace používají starší verze komponenty modelu COM, musíte provést další kroky k jejich nasazení. Toto téma popisuje, jak nasadit izolované součásti COM a referenční nativní součásti (například z Visual Basic 6.0 nebo Visual C++).  
  
 Další informace o nasazení izolované komponenty modelu COM, najdete v části "zjednodušení nasazení aplikací s [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] a COM bez registrace" v [http://msdn.microsoft.com/msdnmag/issues/05/04/RegFreeCOM/default.aspx](http://msdn.microsoft.com/msdnmag/issues/05/04/RegFreeCOM/default.aspx).  
  
## <a name="registration-free-com"></a>COM bez registrace  
 COM bez registrace je novou technologií pro nasazení a aktivaci izolované komponenty modelu COM. Je založena na vložení všechny součásti knihovny typů a informace o registraci, který je obvykle nainstalován do systémového registru do souboru XML nazývaného manifest, uložené ve stejné složce jako aplikace.  
  
 Izolace komponenty modelu COM vyžaduje, aby byla registrována na počítači vývojáře, ale nemusí být registrováno v počítači koncového uživatele. Když Pokud chcete izolovat komponenty modelu COM, všechny je potřeba udělat nastavena jeho referenční **izolované** vlastnost, která má **True**. Ve výchozím nastavení je tato vlastnost nastavena **False**, označující, zda má být zpracovávána jako registrovaný odkaz COM. Pokud je tato vlastnost **True**, způsobí to manifestu má být vygenerován pro tuto součást v čase vytvoření buildu. Také způsobuje, že odpovídající soubory budou zkopírovány do složky aplikace během instalace.  
  
 Pokud generátor manifestu setká s izolovaným odkazem COM, zobrazí všechny `CoClass` položek v součásti knihovny typů, odpovídající každé položky s jeho odpovídající registrační data a generování manifestu definice pro všechny knihovny COM třídy v souboru typu knihovna.  
  
## <a name="deploying-registration-free-com-components-using-clickonce"></a>Nasazování komponent COM bez registrace pomocí ClickOnce  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]technologie nasazení je vhodná pro nasazení izolované komponenty modelu COM, protože obě [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] a COM bez registrace vyžadují, aby součást měla manifest pro nasazení.  
  
 Autor součásti by měl obvykle poskytovat manifestu. Pokud ne, ale je schopen generování manifestu automaticky pro komponenty modelu COM Visual Studio. Generování manifestu je provedeno během [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] publikování procesu; Další informace najdete v tématu [publikování aplikací ClickOnce](../deployment/publishing-clickonce-applications.md). Tato funkce také umožňuje využít starší verzi součásti, které jsou vytvořené v dřívějších vývojových prostředí, jako je například Visual Basic 6.0.  
  
 Existují dva způsoby, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] nasazuje komponenty COM:  
  
-   Zaváděcí nástroj použijte k nasazení komponenty modelu COM; Tento postup funguje na všech podporovaných platformách.  
  
-   Použijte nasazení izolace (také označované jako COM bez registrace) nativní součásti. Ale to bude fungovat pouze v systému Windows XP nebo novější operační systém.  
  
### <a name="example-of-isolating-and-deploying-a-simple-com-component"></a>Příklad izolace a nasazení jednoduché komponenty modelu COM  
 K prokázání nasazení součásti COM bez registrace, bude tento příklad vytvoření aplikace systému Windows v jazyce Visual Basic, který odkazuje na izolovanou nativní součást COM vytvořený pomocí Visual Basic 6.0 a nasadíte ho pomocí [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)].  
  
 Nejdřív je potřeba vytvořit nativní komponenty modelu COM:  
  
##### <a name="to-create-a-native-com-component"></a>Chcete-li vytvořit nativní komponenty modelu COM  
  
1.  Pomocí Visual Basic 6.0 **soubor** nabídky, klikněte na tlačítko **nový**, pak **projektu**.  
  
2.  V **nový projekt** dialogové okno, vyberte **jazyka Visual Basic** uzel a vyberte možnost **ActiveX DLL** projektu. V **název** zadejte `VB6Hello`.  
  
    > [!NOTE]
    >  Jsou podporovány pouze typy projektu knihovny DLL ActiveX a ovládací prvek ActiveX v modelu COM bez registrace; Typy projektů ActiveX EXE a ActiveX dokumentu nejsou podporovány.  
  
3.  V **Průzkumníku řešení**, dvakrát klikněte na **Class1.vb** otevřete textový editor.  
  
4.  V Class1.vb, přidejte následující kód po generovaný kód pro `New` metoda:  
  
    ```  
    Public Sub SayHello()  
       MsgBox "Message from the VB6Hello COM component"  
    End Sub  
    ```  
  
5.  Vytvořte komponentu. Z **sestavení** nabídky, klikněte na tlačítko **sestavit řešení**.  
  
> [!NOTE]
>  COM bez registrace podporuje pouze knihovny DLL a COM řídí typy projektů. Exe nelze použít s-registrační COM.  
  
 Nyní můžete vytvořit aplikace pro systém Windows a přidat odkaz na komponentu COM na ni.  
  
##### <a name="to-create-a-windows-based-application-using-a-com-component"></a>Vytvoření aplikace systému Windows pomocí komponenty modelu COM  
  
1.  Pomocí jazyka Visual Basic **soubor** nabídky, klikněte na tlačítko **nový**, pak **projektu**.  
  
2.  V **nový projekt** dialogové okno, vyberte **jazyka Visual Basic** uzel a vyberte možnost **aplikace Windows**. V **název** zadejte `RegFreeComDemo`.  
  
3.  V **Průzkumníku řešení**, klikněte **zobrazit všechny soubory** pro zobrazení odkazů projektu.  
  
4.  Klikněte pravým tlačítkem myši **odkazy** uzel a vyberte možnost **přidat odkaz na** v místní nabídce.  
  
5.  V **přidat odkaz na** dialogové okno, klikněte na tlačítko **Procházet** , přejděte k VB6Ahoj.dll a potom vyberte ho.  
  
     A **VB6Ahoj** odkaz se zobrazí v seznamu odkazů.  
  
6.  Přejděte **sada nástrojů**, vyberte **tlačítko** řízení a přetáhněte ji do **Form1** formuláře.  
  
7.  V **vlastnosti** nastavte na tlačítko **Text** vlastnost **Hello**.  
  
8.  Dvakrát klikněte na tlačítko Přidat kód pro obslužnou rutinu a v souboru kódu, přidejte kód tak, aby obslužná rutina načte následujícím způsobem:  
  
    ```  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
        Dim VbObj As New VB6Hello.Class1  
        VbObj.SayHello()  
    End Sub  
    ```  
  
9. Spusťte aplikaci. Z **ladění** nabídky, klikněte na tlačítko **spustit ladění**.  
  
 Dále je třeba izolovat ovládacího prvku. Jednotlivé komponenty COM, která vaše aplikace používá je reprezentován ve vašem projektu modelu COM odkaz. Tyto odkazy jsou zobrazeny v **odkazy** uzlu **Průzkumníku řešení** okno. (Všimněte si, že můžete přidat odkazuje buď přímo pomocí **přidat odkaz na** příkaz na **projektu** nabídky, nebo nepřímo přetažením ovládacího prvku ActiveX do svého formuláře.)  
  
 Následující kroky ukazují, jak izolovat komponenty modelu COM a publikujte aktualizovanou aplikaci obsahující izolované ovládacího prvku:  
  
##### <a name="to-isolate-a-com-component"></a>Izolace komponenty modelu COM  
  
1.  V **Průzkumníku řešení**v **odkazy** uzlu, vyberte **VB6Ahoj** odkaz.  
  
2.  V **vlastnosti** okno, změňte hodnotu **izolovaná** vlastnost z **False** k **True**.  
  
3.  Z **sestavení** nabídky, klikněte na tlačítko **sestavit řešení**.  
  
 Teď, když stisknutím klávesy F5, aplikace funguje podle očekávání, ale je nyní spuštěna pod-registrační COM. Aby bylo možné prokázat, zkuste součásti VB6Ahoj.dll a spustit RegFreeComDemo1.exe mimo prostředí Visual Studio IDE. Nyní když po kliknutí na tlačítko, stále funguje. Pokud přejmenujete dočasně manifest aplikace, se znovu nezdaří.  
  
> [!NOTE]
>  Chybí komponenty modelu COM můžete simulovat dočasně zrušení registrace. Otevřete příkazový řádek, přejděte do složky systému zadáním `cd /d %windir%\system32`, potom zrušit registraci součásti zadáním `regsvr32 /u VB6Hello.dll`. Můžete ho znovu zaregistrovat zadáním `regsvr32 VB6Hello.dll`.  
  
 Posledním krokem je k publikování aplikace pomocí [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]:  
  
##### <a name="to-publish-an-application-update-with-an-isolated-com-component"></a>Chcete-li publikovat aktualizace aplikace s izolované komponenty modelu COM  
  
1.  Z **sestavení** nabídky, klikněte na tlačítko **Publikovat RegFreeComDemo**.  
  
     Zobrazí se v Průvodci publikováním.  
  
2.  V Průvodci publikováním zadejte umístění na disku v místním počítači, kde můžete používat a zkontrolujte publikované soubory.  
  
3.  Klikněte na tlačítko **Dokončit** k publikování aplikace.  
  
 Pokud si projdete publikované soubory, budou Všimněte si, zda je soubor sysmon.ocx zahrnuty. Ovládací prvek je zcela izolované aplikace, což znamená, že pokud koncový uživatel počítač jiná aplikace v jiné verzi ovládacího prvku, nemůže rušit tuto aplikaci.  
  
## <a name="referencing-native-assemblies"></a>Odkazování na nativní sestavení  
 Visual Studio podporuje odkazy na nativní Visual Basic 6.0 nebo sestavení C++; Tyto odkazy se nazývají nativní odkazy. Můžete zjistit, zda je odkaz nativní jestli jeho **typ souboru** je nastavena na **nativní** nebo **ActiveX**.  
  
 Chcete-li přidat nativní referenční dokumentace, použijte **přidat odkaz na** příkaz a potom vyhledejte manifest. Některé součásti umístit manifestu do knihovny DLL. V takovém případě můžete jednoduše zvolit samotné knihovny DLL a Visual Studio se ji přidat jako odkaz na nativní pokud zjistí, že součást obsahuje vložený manifest. Visual Studio také automaticky zahrne všechny závislé soubory nebo uvedené v manifestu, pokud jsou ve stejné složce jako součást nástroje odkazované sestavení.  
  
 Izolace ovládacího prvku COM usnadňuje nasazení komponent COM, které již nemají manifesty. Ale pokud součást se dodává s manifestu, můžete odkazovat manifest přímo. Ve skutečnosti byste měli vždycky používat manifest poskytnutý autorem součásti, místo použití **izolovaná** vlastnost.  
  
## <a name="limitations-of-registration-free-com-component-deployment"></a>Omezení nasazení komponenty modelu COM bez registrace  
 COM bez registrace poskytuje jasné výhody oproti tradičním technikám nasazení. Existují však několik omezení a upozornění, které by měl třeba podotknout. Největší omezení je, že funguje pouze v systému Windows XP nebo novější. Implementace COM bez registrace vyžadovala provedení změn ve způsobu, ve kterém jsou načtená součásti v základní operační systém. Bohužel neexistuje žádná podpora nižší úrovně vrstva pro-registrační COM.  
  
 Ne všechny komponenty je vhodným kandidátem pro-registrační COM. Součást není vhodná, pokud platí některá z následujících akcí:  
  
-   Součást je server mimo proces. Nejsou podporované servery EXE; jsou podporovány pouze knihovny DLL.  
  
-   Součást je součástí operačního systému, nebo je součástí systému, jako je například XML, Internet Explorer nebo Microsoft Data Access Components (MDAC). Postupujte podle zásad přerozdělení autora součásti; poraďte s dodavatelem.  
  
-   Součást je součástí aplikace, jako je například Microsoft Office. Například byste neměli izolovat Microsoft Model objektů aplikace Excel. To je součástí systému Office a lze použít pouze v počítači s plnou verzi produktu Office nainstalována.  
  
-   Součást je určena pro použití jako doplněk nebo modul snap-in, například Office add-in nebo ovládacího prvku ve webovém prohlížeči. Tyto součásti obvykle vyžadují nějaký druh registrace schéma definované hostitelského prostředí, které je nad rámec samotného manifestu.  
  
-   Součást spravuje fyzické nebo virtuální zařízení pro systém, například ovladač zařízení pro zařazování tisku.  
  
-   Součást je přístup k datům, která je redistributable. Data aplikace obecně vyžadují oddělené datové redistributable nainstalovat ještě před jejich spuštěním. Byste neměli izolovat komponenty, například ovládací prvek dat ADO Microsoft, Microsoft OLE DB nebo Microsoft Data Access Components (MDAC). Místo toho pokud vaše aplikace používá MDAC nebo SQL Server Express, je třeba je nastavit jako požadavky; v tématu [postupy: instalace předpokladů s aplikací ClickOnce](../deployment/how-to-install-prerequisites-with-a-clickonce-application.md).  
  
 V některých případech může být pro vývojáře součásti možné změnit její návrh pro-registrační COM. Pokud to není možné, můžete pořád vytvářet a publikovat aplikace, které jsou na nich závislé prostřednictvím schéma standardní registraci pomocí zaváděcího nástroje. Další informace najdete v tématu [vytváření balíčků zaváděcího nástroje](../deployment/creating-bootstrapper-packages.md).  
  
 Komponenty modelu COM může být pouze jednou izolované na aplikaci. Například nelze izolovat stejnou součást COM ze dvou různých **knihovny tříd** projekty, které jsou součástí stejné aplikaci. Díky tomu bude mít za následek sestavení upozornění a aplikace se nepodaří načíst v době běhu. Chcete-li se tomuto problému vyhnout, společnost Microsoft doporučuje zapouzdření komponenty modelu COM v jediné knihovny tříd.  
  
 Existuje několik scénářů, ve které COM se vyžaduje registrace na počítači pro vývojáře, přestože nasazení aplikace nevyžaduje registraci. `Isolated` Vlastnost vyžaduje zaregistrovat součást COM na počítači pro vývojáře k automatické generování manifestu během sestavení. Neexistují žádné zachytávání registrací možnosti, které vyvolají Automatická registrace během sestavení. Navíc všechny třídy, které nejsou výslovně definované v knihovně typů neodrazí v manifestu. Při použití komponenty modelu COM s existující manifestu, jako je například nativní referenční dokumentace součást nemusí být registrováno v době vývoje. Registrace je však vyžaduje, pokud součást je ovládací prvek ActiveX a chcete zahrnout do **sada nástrojů** a Návrhář formulářů Windows.  
  
## <a name="see-also"></a>Viz také  
 [ClickOnce – zabezpečení a nasazení](../deployment/clickonce-security-and-deployment.md)
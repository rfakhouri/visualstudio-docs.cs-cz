---
title: Začínáme s diagnostikou grafiky sady Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 05/26/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c2804b07db0b7cf8d01c8578877d4b722d6ceb96
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
ms.locfileid: "31477518"
---
# <a name="getting-started-with-visual-studio-graphics-diagnostics"></a>Začínáme s diagnostikou grafiky sady Visual Studio
V této části budete připravit k použití diagnostiky grafiky poprvé, pak budete zachycení snímků z aplikace Direct3D – a prozkoumejte je Graphics Analyzeru.  
  
## <a name="requirements"></a>Požadavky  
 Pokud chcete používat diagnostiky grafiky v sadě Visual Studio, musíte použít Visual Studio Enterprise, Visual Studio Professional nebo Visual Studio Community.  Jiné edice, včetně Visual Studio Code, neobsahují tuto funkci.
 
 [!INCLUDE[downloadvs](../includes/downloadvs_md.md)]  
  
### <a name="windows-10-prerequisites"></a>Požadavky pro Windows 10  
 Volitelné funkce systému Windows *grafických nástrojů* poskytuje infrastrukturu záznam a přehrávání, který je požadován diagnostiky grafiky ve Windows 10.  
  
 Informace o instalaci nástrojů grafiky najdete v tématu [nainstalovat grafické nástroje pro Windows 10](#InstallGraphicsTools).  
  
##  <a name="InstallGraphicsTools"></a> Instalace nástrojů grafiky pro Windows 10  
 V systému Windows 10, poskytuje infrastrukturu diagnostiky grafiky volitelná funkce systému Windows, nazvaný *grafických nástrojů*. Tato funkce se vyžaduje k zaznamenání a přehrání grafických informací ve Windows 10 bez ohledu na to, jestli aplikace zaznamenávané cíle předchozí verze systému windows nebo kterou verzi Direct3D – používá. Můžete nainstalovat funkce grafické nástroje předem; v opačném případě bude nainstalovaný na vyžádání první čas spuštění relace diagnostiky grafiky sady Visual Studio.  
  
#### <a name="to-install-graphics-tools-for-windows-10"></a>Chcete-li nainstalovat grafické nástroje pro Windows 10  
  
1.  Do pole hledání zadejte **aplikace a funkce** a pak otevřete **aplikace a funkce** nastavení.
  
3.  Na pravé straně **aplikace a funkce** dialogovém okně, vyberte **spravovat volitelné funkce** (v části **aplikace a funkce**).

    **Spravovat volitelné funkce** otevře se dialogové okno.
  
4.  V **spravovat volitelné funkce** dialogovém okně, vyberte **přidání funkce**. Zobrazí se seznam volitelné funkce, které můžete nainstalovat.  
  
5.  Vyberte **grafických nástrojů** ze seznamu funkcí, zvolte **nainstalovat**.  
  
 Funkce grafické nástroje je také automaticky nainstaluje při instalaci Windows 10 SDK.  
  
> [!TIP]
>  Volitelné funkce grafické nástroje Windows 10 poskytuje odlehčený záznam a přehrávání funkce – například programu příkazového řádku zachycení **dxcap.exe**– které mohou být používány podpory, testování a diagnostiky scénáře na počítače, kde nejsou nainstalovány nástroje pro vývojáře. Další informace najdete v tématu [nástroje příkazového řádku snímek](command-line-capture-tool.md) tématu.  
  
## <a name="using-graphics-diagnostics-for-the-first-time"></a>Při prvním použití diagnostiky grafiky  
 Teď, když máte všechny potřebné, jste připravení začít používat diagnostiky grafiky. Postupujte podle těchto kroků.  
  
### <a name="1---create-a-direct3d-app"></a>1 – Vytvoření Direct3D – aplikace  
 Pokud již máte vlastní Direct3D – aplikace a prozkoumejte diagnostiky grafiky, skvěle! Jinak použijte jednu z těchto možností:

- **DirectX 11 aplikace (univerzální pro Windows)** nebo **DirectX 12 aplikace (univerzální pro Windows)** šablony projektu pro Windows 10.
- [Ukázka Direct3D – 12 UAP](https://code.msdn.microsoft.com/Direct3D-12-UAP-Sample-ecb1779f) pro Windows 10.  
  
 Ujistěte se, že můžete vytvořit aplikaci než budete pokračovat.  
  
### <a name="2---start-a-graphics-diagnostics-session"></a>2 – spuštění relace diagnostiky grafiky  
 Nyní jste připraveni začít první relace diagnostiky grafiky. V sadě Visual Studio v hlavní nabídce zvolte **ladit, grafiky, spustit ladění grafiky**, nebo stačí stisknout klávesu **Alt + F5**. To spustí aplikace v rámci diagnostiky grafiky a zobrazí okno diagnostiky relace v sadě Visual Studio.  
  
> [!IMPORTANT]
>  Pokud používáte aplikace ve Windows 10 a volitelné funkce grafické nástroje ještě nenainstalovali, budete vyzváni k udělejte to teď. Musíte ji nainstalovat před použitím diagnostiky grafiky ve Windows 10.  
  
### <a name="3---capture-frames"></a>3 - zachycení snímků  
 Jste připraveni k zachycení snímků při spuštění vaší aplikace.  
  
#### <a name="to-capture-single-frames"></a>K zachycení jeden rámce  
  
-   Ve Visual Studiu zvolte **zachycení rámce** tlačítko z okna nástrojů nebo diagnostiky grafiky relace. Nebo, pokud má vaše aplikace fokus, stačí stisknout klávesu **Print Screen** klíče na klávesnici.
  
#### <a name="to-capture-a-sequence-of-frames"></a>K zachycení pořadí snímků  
  
-   V sadě Visual Studio, v okně diagnostické relace nastavte **rámce pro zachycení** počet snímků, které chcete zachytit v pořadí, pak zachytíte sekvenci pomocí některé z metod popsaných výše pro zachycení jeden rámce.  
  
     Chcete-li znovu zachytit jednu rámce, nastavte **rámce pro zachycení** k *1*.  
  
 Po dokončení sběru rámců právě ukončete aplikaci nebo zvolte **Zastavit** tlačítko z panel nástrojů grafiky nebo okna relace diagnostiky.  
  
### <a name="4---examine-captured-frames-in-the-graphics-analyzer"></a>4 - zkontrolujte zaznamenané rámce v analyzátoru grafiky  
 Nyní jste připraveni zkontrolujte snímky, které právě zaznamenat. Pokud chcete spustit, analýza rámečku, vyberte počet rámce rámce, který chcete prověřit z okna relace diagnostiky. Otevře rámečku v **analyzátor grafiky**, kde můžete pomocí nástroje diagnostiky grafiky zjistit, jak vaše aplikace používá Direct3D – sledovat vykreslování problémy, nebo použít **analýza snímků** nástroj pro Pochopte jeho výkon.  
  
 Pokud jste vybrali nesprávný rámečku z okna relace diagnostiky nebo které chcete prověřit jiného snímku můžete vybrat novou z Graphics Analyzeru. Na **vykreslení cílový** kartě okně protokolu grafiky ve bitovou kopii vykreslení cíl, rozbalte **rámce seznamu** a potom zvolte jiného snímku prozkoumat.  
  
 Další informace o používání nástroje Analyzátor grafiky společně najdete v tématu [příklady](graphics-diagnostics-examples.md).  
  
## <a name="see-also"></a>Viz také  
 [Direct3D – 12 grafiky](http://msdn.microsoft.com/en-us/52094ae3-3b44-4689-9ee7-1ba1b3a779cb)
---
title: "Globalizace a lokalizace v aplikaci Excel řešení | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords: globalization [Office development in Visual Studio], configuring
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 66c997dd8de6801d790b7653ca414cac0996ddc9
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="globalization-and-localization-of-excel-solutions"></a>Globalizace a lokalizace řešení pro Excel
  Tato část obsahuje informace o zvláštní upozornění pro aplikaci Microsoft Office Excel řešení, které se budou spouštět v počítačích s jinou než anglickou nastavení pro Windows. Většinu aspektů globalizace a lokalizace řešení Microsoft Office jsou stejné jako dojde při vytvoření jiných druhů řešení pomocí sady Visual Studio. Obecné informace najdete v tématu [Globalizing a lokalizace aplikací](/visualstudio/ide/globalizing-and-localizing-applications).  
  
 Ve výchozím nastavení hostitelské ovládací prvky v aplikaci Microsoft Office Excel pracovní správně v místní nastavení systému Windows, tak dlouho, dokud všechna data, která je předána ani s nimi manipulovat pomocí spravovaného kódu je naformátován pomocí Czech (Czech Republic) formátování. V projektech cílených [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)], toto chování se řídí modul CLR (CLR).  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="formatting-data-in-excel-with-various-regional-settings"></a>Formátování dat v aplikaci Excel s různými místní nastavení  
 Je třeba naformátovat všechna data, která má závislé na národním prostředí formátování, jako je například kalendářních dat a měny pomocí formátu data Czech (Czech Republic) (národní prostředí ID 1033) před předejte ji do aplikace Microsoft Office Excel nebo číst data z kódu v projektu Office.  
  
 Ve výchozím nastavení při vývoji řešení Office v sadě Visual Studio, model objektů aplikace Excel očekává, národní prostředí ID 1033 data formátování (to se nazývá také uzamčení objektový model pro národní prostředí ID 1033). Toto chování odpovídá způsobu, jakým Visual Basic pro aplikace funguje. Toto chování však lze upravit v řešení v sadě Office.  
  
### <a name="understanding-how-the-excel-object-model-always-expects-locale-id-1033"></a>Pochopení, jak Model objektů aplikace Excel vždy očekává ID národního prostředí 1033  
 Ve výchozím nastavení řešení pro systém Office, které vytvoříte pomocí sady Visual Studio neovlivní nastavení národního prostředí koncového uživatele a vždy chovat, jako kdyby národní prostředí je angličtina (Spojené státy). Například, pokud získání nebo nastavení <xref:Microsoft.Office.Interop.Excel.Range.Value2%2A> vlastností v aplikaci Excel, data musí být ve formátu tak, aby se očekává ID národního prostředí 1033. Pokud používáte jiný datový formát, můžete získat neočekávané výsledky.  
  
 I když použijete formát Czech (Czech Republic) pro data, která je předán nebo manipulovat spravovaného kódu, aplikace Excel interpretuje a zobrazí data správně podle nastavení národního prostředí koncového uživatele. Aplikace Excel můžete formátu dat správně, protože spravovaný kód předá formátu národního prostředí ID 1033 spolu s daty, která označuje, že data jsou v Czech (Czech Republic) a proto musí být naformátována tak, aby odpovídaly nastavení národního prostředí uživatele.  
  
 Například pokud koncoví uživatelé mají svoje místní nastavení nastaven německou prostředí, očekávané datum 29. června 2005, chcete-li být naformátován takto: 29.06.2005. Ale pokud vaše řešení předá data do aplikace Excel jako řetězec, je třeba naformátovat datum podle formátu Czech (Czech Republic): 6/29/2005. Pokud buňky formátována jako datum buňku, aplikace Excel se zobrazí datum ve formátu němčina (Německo).  
  
### <a name="passing-other-locale-ids-to-the-excel-object-model"></a>Předání jiné ID národního prostředí Model objektů aplikace Excel  
 Modul CLR (CLR) automaticky předá ID 1033 národního prostředí pro všechny metody a vlastnosti ve model objektů aplikace Excel, které přijímají národního prostředí důvěrná data. Neexistuje žádný způsob, jak změnit toto chování automaticky pro všechna volání do modelu objektu. Však můžete předat ID národního prostředí jiný do konkrétní metody pomocí <xref:System.Type.InvokeMember%2A> k volání metody a předáním ID národního prostředí, který má *jazykovou verzi* parametru metody.  
  
## <a name="localizing-document-text"></a>Lokalizace textového dokumentu  
 Dokument, šablony nebo sešitu ve vašem projektu pravděpodobně obsahuje statický text, který musí být lokalizované odděleně od sestavení a další spravované prostředky. Přímý způsob, jak to udělat, je vytvořit kopii dokumentu a převede text pomocí aplikace Microsoft Office Word nebo Microsoft Office Excel. Tento proces funguje, i když neprovedete žádné změny kódu, protože může být propojený libovolný počet dokumentů do stejného sestavení.  
  
 Dál musíte zkontrolovat, že libovolná součást váš kód, který komunikuje s textem dokumentu pokračuje tak, aby odpovídaly jazyk textu a že záložky pojmenované oblasti, a další pole zobrazení pojmout všechny přeformátování dokumentu Office, který je nezbytný k Upravte jinou délku gramatika a text. Šablonu dokumentů, které obsahují poměrně málo text můžete zvážit ukládání textu do souborů prostředků a pak načítání textu za běhu.  
  
### <a name="text-direction"></a>Směr textové  
 V aplikaci Excel můžete nastavit vlastnost listu k vykreslení textu zleva doprava. Hostování ovládacích prvků nebo libovolný ovládací prvek, který má `RightToLeft` vlastnost, která se automaticky umístí na návrháře odpovídat tato nastavení za běhu. Není k dispozici nastavení dokumentu obousměrný text (změnit jenom vaše zarovnání textu), takže ovládací prvky nelze mapovat na toto nastavení. Místo toho je nutné nastavit zarovnání textu pro každý ovládací prvek. Je možné napsat kód, který provede všechny ovládací prvky a nutí je k vykreslení textu zprava doleva.  
  
### <a name="changing-culture"></a>Změna jazykovou verzi  
 Kód přizpůsobení na úrovni dokumentu obvykle sdílí hlavního vlákna uživatelského rozhraní aplikace Excel, takže všechny změny provedené u jazykovou verzi vlákna ovlivňuje všechno ostatní, který běží v daném vláknu; Tato změna není omezen na vlastní.  
  
 Ovládací prvky Windows Forms se inicializují před úrovni aplikace VSTO doplňky jsou spouštěné hostitelskou aplikaci. V těchto situacích jazykovou verzi by mělo být změněno před nastavením ovládacích prvků uživatelského rozhraní.  
  
## <a name="installing-the-language-packs"></a>Instalace jazykové sady  
 Pokud používáte jinou než anglickou nastavení pro Windows, můžete nainstalovat [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] jazykových sad zobrazíte [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] zprávy ve stejném jazyce jako Windows. Pokud žádné koncovým uživatelům spustit řešení s jinou než anglickou nastavení pro Windows, musí mít správný jazyková sada zobrazíte runtime zprávy ve stejném jazyce jako Windows. [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] Jazykové sady jsou k dispozici na [Microsoft Download Center](http://www.microsoft.com/downloads).  
  
 Kromě toho jsou nezbytné pro zprávy ClickOnce redistributable jazykových sad rozhraní .NET Framework. Rozhraní .NET Framework jazykové sady jsou k dispozici na [Microsoft Download Center](http://www.microsoft.com/downloads).  
  
## <a name="regional-settings-and-excel-com-calls"></a>Místní nastavení a volání Excelu COM  
 Vždy, když se spravovaným klientem volá metodu na objekt COM a musí se předat informace specifické pro jazykovou verzi, nebude proto pomocí <xref:System.Globalization.CultureInfo.CurrentCulture%2A> (národní prostředí) odpovídající aktuální národní prostředí vlákna. Aktuální národní prostředí vlákna je zděděn z místní nastavení uživatele ve výchozím nastavení. Ale pokud provedete volání do modelu objektů aplikace Excel z aplikace Excel řešení vytvořená pomocí nástrojů pro vývoj pro Office v sadě Visual Studio, formát dat Czech (Czech Republic) (národní prostředí ID 1033) je předán model objektů aplikace Excel automaticky. Je třeba naformátovat všechna data, která má formátování závislé na národním prostředí, například data a měny, formátu dat Czech (Czech Republic) před předejte ji do aplikace Microsoft Office Excel nebo číst data z vašeho kódu projektu.  
  
## <a name="considerations-for-storing-data"></a>Důležité informace pro ukládání dat  
 Chcete, aby vaše data jsou správně interpretovat a zobrazí, měli byste také zvážit, problémy může dojít, když aplikace při ukládání dat, jako je například vzorce sešitu aplikace Excel, v textové literály (pevně zakódované) místo v objektů se silným typem. Měli byste použít dat, který je naformátovaný za předpokladu, že styl neutrální jazykovou verzi nebo angličtinu (Spojené státy) (LCID hodnota 1033).  
  
### <a name="applications-that-use-string-literals"></a>Aplikace, které používají textové literály  
 Možné hodnoty, které mohou být pevně zahrnují literály data, které jsou zapsány ve formátu Czech (Czech Republic) a vzorce sešitu aplikace Excel, které obsahují funkce lokalizované názvy. Další možností může být pevně řetězec, který obsahuje počet třeba "1 000"; v některých jazykových verzí to interpretována jako jeden tisíc, ale v jiné jazykové verze, představuje jeden bod nula. Výpočty a porovnání provést v má nesprávný formát může mít za následek nesprávná data.  
  
 Aplikace Excel interpretuje všechny řetězce v souladu s LCID, který je předán řetězcem. Může to být problém, pokud neodpovídá žádnému formát řetězce LCID, který je předán. Při předávání všechna data, vytvořili pomocí nástroje pro vývoj pro Office v sadě Visual Studio řešení pro aplikaci Excel použít LCID 1033 (en US). Zobrazí aplikace Excel dat podle místní nastavení a jazyk uživatelského rozhraní aplikace Excel. Visual Basic for Applications (VBA) funguje i tímto způsobem; řetězce jsou formátovány jako en US a VBA téměř vždy předá 0 (jazykově neutrální) jako identifikátor LCID. Například následující kód VBA zobrazí hodnotu správně naformátován na 12 může 2004, v souladu s aktuální nastavení národního prostředí uživatele:  
  
```  
'VBA  
Application.ActiveCell.Value2 = "05/12/04"  
```  
  
 Stejný kód, když se používá v řešení vytvořená pomocí nástrojů pro vývoj pro Office v sadě Visual Studio a předává do aplikace Excel pomocí zprostředkovatele komunikace s objekty COM, vytvoří stejné výsledky při datum formátována ve stylu en US.  
  
 Příklad:  
  
 [!code-vb[Trin_VstcoreCreatingExcel#6](../vsto/codesnippet/VisualBasic/Trin_VstcoreCreatingExcelVB/Sheet1.vb#6)]
 [!code-csharp[Trin_VstcoreCreatingExcel#6](../vsto/codesnippet/CSharp/Trin_VstcoreCreatingExcelCS/Sheet1.cs#6)]  
  
 Měli byste spolupracovat s místo textové literály, kdykoli je to možné dat silného typu. Například místo ukládání datum v řetězcový literál, uložte ho jako <xref:System.Double>, poté převeďte ho na <xref:System.DateTime> objekt pro zpracování.  
  
 Následující příklad kódu trvá datum, které uživatel zadá do buňky A5, uloží ji jako <xref:System.Double>, potom převede jej na <xref:System.DateTime> objekt pro zobrazení v buňce A7. Zobrazí datum musí být ve formátu A7 buňky.  
  
 [!code-vb[Trin_VstcoreCreatingExcel#7](../vsto/codesnippet/VisualBasic/Trin_VstcoreCreatingExcelVB/Sheet1.vb#7)]
 [!code-csharp[Trin_VstcoreCreatingExcel#7](../vsto/codesnippet/CSharp/Trin_VstcoreCreatingExcelCS/Sheet1.cs#7)]  
  
### <a name="excel-worksheet-functions"></a>Funkce listu aplikace Excel  
 Názvy funkcí listu jsou převedeny interně pro většinu jazykové verze Excelu. Ale kvůli potenciální jazyk a problémy zprostředkovatele komunikace s objekty COM důrazně doporučujeme použít názvy pouze anglické funkce ve vašem kódu.  
  
### <a name="applications-that-use-external-data"></a>Aplikace, které používají externích dat  
 Kód, který otevře nebo jinak používá externí data, jako jsou například soubory, které zahrnují hodnot oddělených čárkami (CSV soubory) exportovat ze starší verze systému, může mít vliv i, pokud tyto soubory jsou exportovány žádné formátu kromě en US. Přístup k databázi nemusí mít vliv, protože všechny hodnoty musí být v binárním formátu, pokud databáze ukládá kalendářních dat jako řetězce nebo provádí operace, které nepoužívají binární formát. Vytváříte dotazy SQL pomocí dat z aplikace Excel, může také muset ověřte, že jsou ve formátu en US, v závislosti na funkce, které používáte.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: cíle vícejazyčné uživatelské rozhraní Office](../vsto/how-to-target-the-office-multilingual-user-interface.md)   
 [Návrh a vytváření řešení pro systém Office](../vsto/designing-and-creating-office-solutions.md)   
 [Volitelné parametry v řešeních pro systém Office](../vsto/optional-parameters-in-office-solutions.md)  
  
  
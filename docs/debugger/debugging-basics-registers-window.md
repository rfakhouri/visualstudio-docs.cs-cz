---
title: O okně registr | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- Registers window, about Registers window
- debugging [Visual Studio], Registers window
ms.assetid: ab354047-053e-4f94-8ac1-26e761442b6f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 37b2c34971750d8e6db0173f6034342b9efbfd97
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
---
# <a name="about-the-registers-window-in-visual-studio"></a>O okně registr v sadě Visual Studio
**Zaregistruje** okno je k dispozici pouze v případě, že je povoleno ladění úrovni adresu v **možnosti** dialogové okno, **ladění** uzlu.  
  
 Registry jsou speciální umístění v rámci procesoru (CPU), které se používají k ukládání dat, která procesor aktivně pracuje na malé části. Kompilování nebo interpretace zdrojový kód generuje pokyny, které přesun dat z paměti do registry a zpět znovu, podle potřeby. Přístup k datům v registrech je velmi rychlé ve srovnání s přístup k datům v paměti, proto obvykle spouštět rychleji než kód, který vyžaduje procesor, neustále zavedení a uvolnění zaregistruje kód, který umožňuje procesoru a ponechat data v rejstříku opakovaně k němu přístup. Aby bylo snazší pro kompilátor ponechat data v registrech a provádět další optimalizace, by měl nepoužívejte globální proměnné a závisí na lokální proměnné co nejvíc. Kód zapisovaný tímto způsobem se říká mají dobrou polohu odkazu. V některých jazycích, například C/C++ může programátorů deklarovat proměnnou registrace, která určuje, kompilátor a zkuste to je nejlepší zachovat proměnnou v rejstříku za všech okolností. Další informace najdete v tématu [zaregistrovat – klíčové slovo](http://msdn.microsoft.com/en-us/5b66905a-2f7f-4918-bb55-5e66d4bc50f9).  
  
 Zaregistruje je možné rozdělit do dvou typů: obecné účely a speciální účel. Pro obecné účely registry obsahovat data pro obecné operace, například přidávání dvou čísel společně nebo odkazující na element v matici. Zaregistruje speciální mají zvláštní účely a speciální význam. Dobrým příkladem je ukazatel zásobníku registr, která procesor používá ke sledování zásobníku volání programu. Jako programátory bude ukazatel zásobníku upravit pravděpodobně není přímo. Je však nezbytné pro správné fungování vašeho programu, protože bez ukazatel zásobníku, nebude procesor věděli, kde se vraťte do na konci volání funkce.  
  
 Většina pro obecné účely registry obsahovat pouze jeden datový prvek. Například jednom celé číslo, číslo s plovoucí desetinnou čárkou nebo element pole. Některé novější procesory mít větší zaregistruje, se nazývá vektoru registrů, které mohou být uloženy malé pole dat. Protože drží množství dat., vector registry povolit operací zahrnujících pole provést velmi rychle. Vector registry nejdřív na levnější a vysoce výkonné superpočítačů používaly ale se stávají nyní k dispozici na procesory, kde se používají k skvělé využít v grafické operace náročné na prostředky.  
  
 Procesor obvykle má dvě sady pro obecné účely registrů, jeden optimalizovaným pro operace s plovoucí desetinnou čárkou a druhou pro operace celé číslo. Logicky toto nastavení se nazývá s plovoucí desetinnou čárkou a zaregistruje celé číslo.  
  
 Spravovaný kód je kompilované za běhu do nativního kódu, který má přístup k fyzické registry mikroprocesoru. **Zaregistruje** okně se zobrazí tyto fyzické zaregistruje se pro modul common language runtime nebo nativního kódu. **Zaregistruje** okno nezobrazí informace o registraci pro skript nebo aplikaci SQL, protože skript a SQL jsou jazyky, které nepodporují koncept registrů.  
  
 Další informace o zobrazení **zaregistruje** okně najdete v části [pomocí okna zaregistruje](../debugger/how-to-use-the-registers-window.md).  
  
 Když se podíváte na **zaregistruje** okno, zobrazí se položky, jako je například v tomto příkladu:  
  
```  
EAX = 003110D8  
```  
  
 Symbol nalevo od přihlašovací = je název registrace, EAX, v tomto případě. Toto číslo napravo od přihlašovací = představuje obsah registrace.  
  
 **Zaregistruje** okno umožňuje provést více než jen zobrazení obsah registru. Pokud jste v režimu pozastavení v nativním kódu, můžete kliknutím na obsah registru a upravit hodnotu. To však není něco, které byste měli udělat náhodně. Pokud budete rozumět tomu, registrace, který upravujete a k datům, které obsahuje, je pravděpodobně selhání programu nebo jiné nežádoucí důsledkem výsledek careless úpravy. Bohužel podrobné vysvětlení registrace sady různé procesory Intel a kompatibilní s Intel přejde daleko nad rámec Tento stručný úvod.  
  
## <a name="register-groups"></a>Skupiny registru  
 Pro lepší přehlednost, **zaregistruje** okno uspořádá zaregistruje do skupin. Pokud jste klikněte pravým tlačítkem na **zaregistruje** okně se zobrazí místní nabídku obsahující seznam skupin, které můžete zobrazit nebo skrýt podle svých potřeb.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: použití okna registry](../debugger/how-to-use-the-registers-window.md)   
 [Základy ladicího programu](../debugger/debugger-basics.md)
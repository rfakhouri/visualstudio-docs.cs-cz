---
title: 'CA2000: Uvolňujte objekty před ztrátou oboru'
ms.date: 05/14/2019
ms.topic: reference
f1_keywords:
- CA2000
- Dispose objects before losing scope
- DisposeObjectsBeforeLosingScope
helpviewer_keywords:
- CA2000
- DisposeObjectsBeforeLosingScope
ms.assetid: 0c3d7d8d-b94d-46e8-aa4c-38df632c1463
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 732b3d683802c50042ee40fee1549a9d247e2470
ms.sourcegitcommit: 283f2dbce044a18e9f6ac6398f6fc78e074ec1ed
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/16/2019
ms.locfileid: "65804980"
---
# <a name="ca2000-dispose-objects-before-losing-scope"></a>CA2000: Uvolňujte objekty před ztrátou oboru

|||
|-|-|
|TypeName|DisposeObjectsBeforeLosingScope|
|CheckId|CA2000|
|Kategorie|Microsoft.Reliability|
|Narušující změna|Nenarušující|

## <a name="cause"></a>Příčina

Místní objekt typu <xref:System.IDisposable> typ je vytvořen, ale není uvolněn předtím, než jsou všechny odkazy na objekt mimo rozsah.

## <a name="rule-description"></a>Popis pravidla

Pokud není uvolnitelný objekt explicitně odstraněn před tím, než jsou všechny odkazy mimo rozsah, bude objekt odstraněn v době, kdy bude systémem uvolňování paměti spuštěna finalizační metoda objektu. Vzhledem k tomu, že může dojít k mimořádné události, která zabrání spuštění finalizační metody objektu, měl by namísto toho být objekt explicitně odstraněn.

### <a name="special-cases"></a>Zvláštní případy

I v případě není uvolněn neaktivuje pro místní objekty z následujících typů pravidla CA2000:

- <xref:System.IO.Stream?displayProperty=nameWithType>
- <xref:System.IO.TextReader?displayProperty=nameWithType>
- <xref:System.IO.TextWriter?displayProperty=nameWithType>
- <xref:System.Resources.IResourceReader?displayProperty=nameWithType>

Předání objektu jednoho z těchto typů konstruktoru a pak ji přiřadíte do pole označuje *dispose převod vlastnictví* do nově konstruovaný typ. To znamená je nově konstruovaný typ nyní zodpovědná za uvolnění objektu. Pokud váš kód předá konstruktoru objektu jednoho z těchto typů, žádná porušení pravidla CA2000 dojde i v případě není uvolněn před všechny odkazy na ni se pokyny neposkytují.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

Chcete-li vyřešit porušení tohoto pravidla, musíte zavolat na objekt metodu <xref:System.IDisposable.Dispose%2A> před tím, než jsou všechny odkazy na něj mimo rozsah.

Můžete použít [ `using` příkaz](/dotnet/csharp/language-reference/keywords/using-statement) ([ `Using` ](/dotnet/visual-basic/language-reference/statements/using-statement) v jazyce Visual Basic) ke sbalení objekty, které implementují <xref:System.IDisposable>. Objekty, které jsou zabaleny tímto způsobem jsou automaticky uvolněna na konci `using` bloku. Ale v následujících případech by neměla nebo nelze zpracovat pomocí `using` – příkaz:

- Pokud chcete vrátit uvolnitelný objekt, musí objekt vytvořen v `try/finally` blokovat mimo `using` bloku.

- Neinicializujte členů uvolnitelného objektu v konstruktoru `using` příkazu.

- Když jsou vnořené konstruktory, které jsou chráněny pouze jednou obslužnou rutinou výjimky v [pořízení součástí `using` příkaz](/dotnet/csharp/language-reference/language-specification/statements#the-using-statement), může způsobit selhání v konstruktoru vnější objekt vytvořený pomocí konstruktoru vnořené nikdy dochází k uzavření. V následujícím příkladu, selhání <xref:System.IO.StreamReader> konstruktor může vést k <xref:System.IO.FileStream> objekt nebude nikdy uzavřen. Výskyt upozornění CA2000 příznaky v tomto případě porušení tohoto pravidla.

   ```csharp
   using (StreamReader sr = new StreamReader(new FileStream("C:\myfile.txt", FileMode.Create)))
   { ... }
   ```

- Dynamické objekty by měly používat stínový objekt implementovat vzor dispose <xref:System.IDisposable> objekty.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Nepotlačujte upozornění tohoto pravidla, pokud:

- Jste volali metodu na objekt, který volá `Dispose`, jako například <xref:System.IO.Stream.Close%2A>
- Metoda, která vyvolala upozornění vrátí <xref:System.IDisposable> objekt zabalující objekt
- Metoda přidělení nemá metodu dispose vlastnictví; To znamená ale zodpovědnost za uvolnění objektu bude převeden na jiném objektu nebo obálky, který byl vytvořen v metodě a vrátit zpět volajícímu

## <a name="related-rules"></a>Související pravidla

- [CA2213: Uvolnitelné pole by mělo být uvolněno](../code-quality/ca2213-disposable-fields-should-be-disposed.md)
- [CA2202: Neuvolňujte objekty několikrát](../code-quality/ca2202-do-not-dispose-objects-multiple-times.md)

## <a name="example"></a>Příklad

Pokud implementujete metody, která vrací uvolnitelný objekt, ujistěte se, že objekt je uvolněn pomocí bloku try/finally bez použití bloku catch. Pomocí bloku try/finally lze povolit vyvolání výjimek v místě selhání a zajistit, aby byl objekt uvolněn.

V metodě OpenPort1 se volání za účelem otevření objektu ISerializable SerialPort nebo volání metody SomeMethod nemusí zdařit. V této implementaci je vyvoláno upozornění CA2000.

V metodě OpenPort2 jsou deklarovány dva objekty SerialPort a jsou nastaveny na hodnotu null:

- Objekt `tempPort`, který se používá k testování toho, zda operace metody proběhly úspěšně.

- Objekt `port`, který se používá pro návratovou hodnotu metody.

Objekt `tempPort` je vytvořen a otevřen v rámci bloku `try` a jakákoli jiná požadovaná činnost je vykonána v rámci stejného bloku `try`. Na konci bloku `try` je otevřený port přiřazen objektu `port`, který bude vrácen, a objekt `tempPort` je nastaven na hodnotu `null`.

Blok `finally` ověřuje hodnotu `tempPort`. Pokud hodnota není null, operace se v rámci metody nezdařila a blok `tempPort` je uzavřen, aby bylo možné zajistit uvolnění jakýchkoli prostředků. Vrácený objekt portu bude obsahovat otevřený objekt SerialPort, pokud byly operace metody úspěšné, nebo bude mít hodnotu null, pokud se operace nezdaří.

```csharp
public SerialPort OpenPort1(string portName)
{
   SerialPort port = new SerialPort(portName);
   port.Open();  //CA2000 fires because this might throw
   SomeMethod(); //Other method operations can fail
   return port;
}

public SerialPort OpenPort2(string portName)
{
   SerialPort tempPort = null;
   SerialPort port = null;
   try
   {
      tempPort = new SerialPort(portName);
      tempPort.Open();
      SomeMethod();
      //Add any other methods above this line
      port = tempPort;
      tempPort = null;

   }
   finally
   {
      if (tempPort != null)
      {
         tempPort.Close();
      }
   }
   return port;
}
```

```vb
Public Function OpenPort1(ByVal PortName As String) As SerialPort

   Dim port As New SerialPort(PortName)
   port.Open()    'CA2000 fires because this might throw
   SomeMethod()   'Other method operations can fail
   Return port

End Function

Public Function OpenPort2(ByVal PortName As String) As SerialPort

   Dim tempPort As SerialPort = Nothing
   Dim port As SerialPort = Nothing

   Try
      tempPort = New SerialPort(PortName)
      tempPort.Open()
      SomeMethod()
      'Add any other methods above this line
      port = tempPort
      tempPort = Nothing

   Finally
      If Not tempPort Is Nothing Then
         tempPort.Close()
      End If

   End Try

   Return port

End Function
```

## <a name="example"></a>Příklad

Kompilátor jazyka Visual Basic má ve výchozím nastavení všechny aritmetické operátory kontrola přetečení. Proto může jakákoli aritmetická operace jazyka Visual Basic vyvolat výjimku <xref:System.OverflowException>. To může vést k neočekávaným případům porušování pravidel, jako je například CA2000. Například následující funkce CreateReader1 ohlásí porušení pravidla CA2000, protože kompilátor jazyka Visual Basic generuje dodatečnou instrukci kontroly přetečení, jež může vyvolat výjimku, která může způsobit, že StreamReader nebude odstraněn.

Chcete-li tento problém vyřešit, můžete zakázat generování kontrol přetečení kompilátorem jazyka Visual Basic v rámci projektu nebo upravit kód tak, jak je tomu v následující funkci CreateReader2.

Pokud chcete zakázat generování kontrol přetečení, klikněte pravým tlačítkem na název projektu v Průzkumníku řešení a potom klikněte na **vlastnosti**. Klikněte na tlačítko **kompilaci**, klikněte na tlačítko **Upřesnit možnosti kompilace**a potom zkontrolujte **odebrat kontroly přetečení celých čísel**.

[!code-vb[FxCop.Reliability.CA2000.DisposeObjectsBeforeLosingScope#1](../code-quality/codesnippet/VisualBasic/ca2000-dispose-objects-before-losing-scope-vboverflow_1.vb)]

## <a name="see-also"></a>Viz také:

- <xref:System.IDisposable>
- [Vzor pro metodu Dispose](/dotnet/standard/design-guidelines/dispose-pattern)
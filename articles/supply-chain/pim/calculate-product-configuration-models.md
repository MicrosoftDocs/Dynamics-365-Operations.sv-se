---
title: Frågor och Svar - Beräkningar för produktkonfigurationsmodeller
description: Det här ämnet beskriver beräkningar för produktkonfigurationsmodeller och förklarar hur du använder beräkningar tillsammans med begränsningar.
author: cvocph
manager: tfehr
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PCConstraintEditor, PCProductConfigurationModelDetails, PCRuntimeConfigurator
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19191
ms.assetid: 8993f9a1-d1c0-49f5-afd3-5e1077ded0fe
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 08eeb1c39150ae9a2fa19b7db5f3206f38a7175e
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5221905"
---
# <a name="calculations-for-product-configuration-models-faq"></a>Frågor och Svar - Beräkningar för produktkonfigurationsmodeller

[!include [banner](../includes/banner.md)]

Det här ämnet beskriver beräkningar för produktkonfigurationsmodeller och förklarar hur du använder beräkningar tillsammans med begränsningar.

Beräkningar kan användas för aritmetiska eller logiska operationer. De kompletterar uttryckbegränsningar i produktkonfigurationsmodeller. Du kan definiera beräkningar på sidan **Detaljer för begränsningsbaserad produktkonfigurationsmodell** och sedan skapa uttryck för beräkningar i uttrycksredigeraren. Mer information finns i Skapa beräkningar.

## <a name="what-is-a-calculation"></a>Vad är en beräkning?
En beräkning är ett element som du kan använda i en produktkonfigurationsmodell. Beräkningar kompletterar begränsningar genom att du kan använda decimaltal till beräkna värden med decimaltal när du konfigurerar en produkt. Vidare har beräkningar en större uppsättning tillgängliga operatorer än begränsningar.  

Likt en begränsning associeras en beräkning med en viss komponent i en modell för produktkonfiguration, och den kan inte återanvändas av eller delas med en annan komponent. En viktig skillnad mellan beräkningar och begränsningar är att beräkningar är absolut nödvändiga (enkelriktade), medan begränsningar är deklarativa (dubbelriktade). Mer information om begränsningar finns i [Uttrycksbegränsningar och registerbegränsningar i modeller för produktkonfiguration](expression-constraints-table-constraints-product-configuration-models.md).  

En beräkning består av ett målattribut och ett beräkningsuttryck.

## <a name="what-is-a-target-attribute"></a>Vad är ett målattribut?
Ett målattribut är ett attribut som tar emot beräkningens resultat i ett uttryck.  

I följande uttryck är målattributet ett bordsdukmått:  

**Uttryck:** Om\[decimalAttribute1 &lt;= decimalAttribute2, True, False\]  

**DecimalAttribute1** är registerlängden, och **decimalAttribute2** är tablecloth-längden. Detta uttryck returnerar värdet **Sant** till målattributet om **decimalAttribute2** är större än eller lika med **decimalAttribute1**. Annars returnerar uttrycket värdet **Falskt**. Så bordduksmåttet är godtagbart om borddukslängden är lika med eller överstiger längden på bordet.

## <a name="what-attribute-types-can-be-set-to-target-attributes"></a>Vilka attributtyper kan ställas in som målattribut?
Alla attributtyper som stöds för produktkonfigureraren kan anges som målattribut med undantag för text utan en fast lista.

## <a name="can-the-value-of-a-target-attribute-restrict-the-values-of-the-input-attributes-in-a-calculation"></a>Kan ett värde för målattributet begränsa värdena för indataattributen i en beräkning?
Nej, ett värde för målattributet kan inte begränsa värdena för indataattributen eftersom beräkningar är enkelriktade. Därför anges värdet för målattributet utifrån ändringar i värdet för indataattributen, men en ändring i målets värde påverkar inte värdet för indataattributen. Detta beteende skiljer sig från beteendet för begränsningar. Begränsningar sker i båda riktningar.

### <a name="example"></a>Exempel

I följande uttryck är målet för beräkningen längden på en elsladd, och indatavärdet är en färg:  

**Uttryck:** \[If Color == "Green", 1.5, 1.0\]  

När du konfigurerar artikeln, anges elsladdens längd som **1,5** om du anger **Grön** som värdet för färgattributet. Om du anger en annan färg, är längden **1,0**. Eftersom beräkningar är enkelriktade ställer beräkningen inte in värdet för färgattributet till **Grön** när du anger en längd på **1,5**.

## <a name="what-happens-if-a-calculation-has-a-target-attribute-of-the-integer-type-but-a-calculation-generates-a-decimal-number"></a>Vad händer om en beräkning har ett målattribut av heltalstypen men en beräkning skapar ett decimaltal?
Om ett målattribut är av heltalstypen, men en beräkning skapar ett decimaltal, returneras bara heltalsdelen på det beräknade resultatet. Decimalerdelen tas bort och resultatet avrundas inte. Ett resultat på 12,70 visas till exempel som 12.

## <a name="when-do-calculations-occur"></a>När sker beräkningar?
Beräkningar sker när ett värde har angetts för alla indataattribut.

## <a name="can-i-overwrite-the-value-that-is-calculated-for-the-target-attribute"></a>Kan jag skriva över värdet som beräknas för målattributet?
Du kan åsidosätta värdet som beräknas för målattributet, om inte målattributet är inställt som dolt eller skrivskyddat.

## <a name="how-do-i-set-a-target-attribute-as-hidden-or-read-only"></a>Hur kan jag ange ett målattribut som dolt eller skrivskyddat?
Om du vill ange ett attribut som dolt eller skrivskyddat, följ dessa steg:

1.  Klicka på **Produktinformationshantering** &gt; **Allmänt** &gt; **Produktkonfigurationsmodeller**.
2.  Välj en modell för produkt, konfiguration och klicka sedan på **Redigera** i åtgärdsfönstret.
3.  På sidan **Detaljer för begränsningsbaserad produktkonfigurationsmodell** väljer du det attribut som du vill använda som målattribut.
4.  På snabbfliken **Attribut** väljer du **Dolt** eller **Skrivskyddat**.

## <a name="can-a-calculation-overwrite-the-values-that-i-set"></a>Kan en beräkning skriva över de värden som jag har angett?
Nr. De värden du anger när du konfigurerar en produkt är de värden som används. Beräkningen som infaller när indatavärdena i beräkningen ändras kan inte skriva över värdena som du anger för ett visst attribut.

## <a name="what-happens-if-i-remove-an-input-value-in-a-calculation"></a>Vad händer om jag tar bort ett invärde i en beräkning?
Om du tar bort ett invärde i en beräkning, tas värdet för målattributet också bort.

## <a name="why-do-i-receive-an-error-message-that-says-that-my-model-is-in-contradiction"></a>Varför jag får ett felmeddelande om att min modell utgör en motsättning?
Detta meddelande visas när en beräkning innehåller ett fel eller om en motsättning förekommer i en eller flera begränsningar. Mer information om motsägelser finns i [Uttrycksbegränsningar och registerbegränsningar i modeller för produktkonfiguration](expression-constraints-table-constraints-product-configuration-models.md). Nedan följer några situationer där det kan uppstå fel i beräkningar:

-   Ett värde delas med 0 (noll).
-   Det finns en konflikt mellan följande två element:
    -   De värden som är tillgängliga för ett attribut och som har begränsningar.
    -   Ett värde som genereras av en beräkning.
-   Värdena som returneras av beräkningen ligger utanför domänen för attributet. Ett exempel är ett heltal mellan \[1..10\] som beräknas till 0.

## <a name="why-do-i-receive-an-error-message-even-though-i-successfully-validated-my-product-model"></a>Varför får jag ett felmeddelande även om jag validerade min produktmodell?
Beräkningar inkluderas inte i valideringen. Du måste testa produktkonfigurationsmodellen för att hitta fel i beräkningar. Följande steg beskriver hur man testar en produktkonfigurationsmodell.

1.  Klicka på **Produktinformationshantering** &gt; **Allmänt** &gt; **Produktkonfigurationsmodeller**.
2.  Välj en produktkonfigurationsmodell i åtgärdsfönstret och klicka sedan på gruppen **Kör**, klicka på **Test**.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]
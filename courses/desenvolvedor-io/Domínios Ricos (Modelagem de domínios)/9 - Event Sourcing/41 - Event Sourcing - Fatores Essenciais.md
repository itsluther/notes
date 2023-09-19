1. Todos os eventos dizem sobre o que houve no passado:
    - No Event Sourcing, todos os eventos representam o que aconteceu no passado e são registros imutáveis das ações que afetaram o estado de uma entidade.
2. Eventos são uma expressão da linguagem ubíqua:
    - É importante que os eventos sejam definidos usando uma linguagem compartilhada entre todas as partes interessadas (ubíqua) para garantir um entendimento comum.
3. Não são imperativos e utilizam verbos no passado:
    - Os eventos descrevem o que ocorreu no passado e, portanto, são formulados no tempo passado. Eles não são instruções para alterar o estado atual da entidade, mas registros históricos.
4. Eventos são sempre adicionados, nunca excluídos:
    - Nos sistemas de Event Sourcing, os eventos são anexados a um registro de eventos e nunca são excluídos ou alterados. Isso garante um histórico completo e imutável.
5. É possível realizar o "Replay" para conhecer o estado anterior da entidade:
    - O "Replay" envolve a reexecução de todos os eventos no histórico para reconstruir o estado atual da entidade a partir do zero. Isso permite obter o estado anterior da entidade a qualquer ponto no tempo.

**Exemplo de replay em C#:**

```C#
public IEnumrable<GenericEventWrapper> GetEventStream(String id)
{
	return DocumentSession
			.Query<GenericEventWrapper>()
			.Where(t => t.AggregateId == id)
			.OrderBy(t => t.Timestamp)
			.ToList();
}
```

```C#
public static Aggregate PlayEvents(String id, IEnumerable<DomainEvent> events)
{
	var aggregate = new Aggregate(id);
	foreach (var e in events)
	{
		if (e is AggregateCreatedEvent)
			aggregate.Create(e.Data);
		if (e is AggregateUpdateEvent)
			aggregate.Update(e.Data);
		if (e is AggregateDeletedEvent)
			aggregate.Delete(e.Data);
	}
	return aggregate;
}
```

6. Caso a história do evento seja muito extensa, pode ser realizado um snapshot:
    - Em sistemas de Event Sourcing com históricos muito longos, criar snapshots periódicos do estado do agregado pode melhorar o desempenho ao reduzir a quantidade de eventos que precisam ser reaplicados durante a reconstrução. Os snapshots são capturas do estado em um ponto específico no tempo.
7. Serializando o estado do agregado até determinado ponto no tempo:
    - Para criar um snapshot, é necessário serializar o estado do agregado em um formato que possa ser armazenado de maneira eficiente. A serialização envolve transformar o estado do agregado (que pode ser uma estrutura de dados complexa) em uma representação mais simples que pode ser armazenada e recuperada rapidamente.
8. Realizando o replay a partir de um determinado snapshot:
    - Após criar um snapshot, você pode realizar o replay a partir desse ponto, aplicando apenas os eventos que ocorreram após o snapshot. Isso economiza tempo e recursos, pois você não precisa reconstruir o estado completo desde o início.

**Event Sourcing é complicado?**
- Utilize um Event-based Data Store, como por exemplo Event Store.

---
[[42 - Event Sourcing Prática - Repositório GitHub]]
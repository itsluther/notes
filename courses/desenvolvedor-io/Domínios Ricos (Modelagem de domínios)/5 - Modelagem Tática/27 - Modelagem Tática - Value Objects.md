**Value Objects (Objetos de Valor)**

- Os Value Objects representam uma coleção de dados individuais que são tratados como um único valor dentro do domínio.
- Eles são destinados a ser uma coleção de atributos que descrevem uma característica do domínio, mas não possuem uma identidade própria. Ou seja, eles são identificados pelos seus valores e não por uma chave única, como acontece com as entidades.
- Value Objects são imutáveis, o que significa que seus valores não podem ser alterados após a criação. Isso garante a estabilidade dos dados e evita efeitos colaterais inesperados.
- São mais precisos do que os tipos primitivos, pois podem encapsular regras de validação e comportamentos específicos do domínio.
- É uma prática recomendada usar Value Objects para representar conceitos que não têm identidade única, como datas, endereços, números de telefone, CPF, etc.

**Vantagens de usar Value Objects:**

- **Construtores:** Value Objects geralmente possuem construtores que garantem que apenas valores válidos possam ser criados, ajudando a evitar estados inconsistentes.
- **Constantes Max e Min:** É possível definir constantes Max e Min dentro do Value Object para limitar os valores possíveis, fornecendo um controle mais rigoroso.
- **Ad hoc setters com lógica de validação:** Você pode implementar lógica de validação personalizada em seus setters para garantir que os valores permaneçam válidos.
- **Ad hoc getters:** Value Objects podem fornecer métodos para recuperar informações específicas de maneira conveniente.
- **Propriedades adicionais:** Além dos atributos principais, você pode adicionar propriedades adicionais aos Value Objects para facilitar o uso e a manipulação dos dados dentro do domínio.

```typescript
class CPF {
  private readonly numero: string;

  constructor(numero: string) {
    if (this.validarCPF(numero)) {
      this.numero = numero;
    } else {
      throw new Error("CPF inválido");
    }
  }

  private validarCPF(numero: string): boolean {
    // Implemente a lógica de validação do CPF aqui
    // Retorne true se o CPF for válido, caso contrário, retorne false
    // Você pode usar bibliotecas externas ou implementar sua própria validação
    // Neste exemplo, faremos uma validação simples para fins ilustrativos

    // Remova caracteres não numéricos do CPF
    const cpfLimpo = numero.replace(/\D/g, "");

    // Verifique se o CPF tem 11 dígitos
    if (cpfLimpo.length !== 11) {
      return false;
    }

    // Verifique se todos os dígitos são iguais (CPF inválido)
    if (/^(\d)\1{10}$/.test(cpfLimpo)) {
      return false;
    }

    // Cálculo do dígito verificador
    let soma = 0;
    for (let i = 0; i < 9; i++) {
      soma += parseInt(cpfLimpo.charAt(i)) * (10 - i);
    }
    const resto = soma % 11;
    const digitoVerificador1 = resto < 2 ? 0 : 11 - resto;

    soma = 0;
    for (let i = 0; i < 10; i++) {
      soma += parseInt(cpfLimpo.charAt(i)) * (11 - i);
    }
    const resto2 = soma % 11;
    const digitoVerificador2 = resto2 < 2 ? 0 : 11 - resto2;

    // Verifique se os dígitos verificadores estão corretos
    if (
      parseInt(cpfLimpo.charAt(9)) !== digitoVerificador1 ||
      parseInt(cpfLimpo.charAt(10)) !== digitoVerificador2
    ) {
      return false;
    }

    return true;
  }

  getNumero(): string {
    return this.numero;
  }
}

// Exemplo de uso
try {
  const cpf = new CPF("123.456.789-09");
  console.log("CPF válido:", cpf.getNumero());
} catch (error) {
  console.error(error.message);
}
```

---
[[28 - Modelagem Tática - Entidades]] - #ddd #domínios-ricos  #modelagem-tatica 
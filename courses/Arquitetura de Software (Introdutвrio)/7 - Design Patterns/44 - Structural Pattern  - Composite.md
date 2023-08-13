O padrão de design Composite é um padrão estrutural que permite tratar objetos individuais e composições de objetos de maneira uniforme. Ele fornece uma forma de compor objetos em estruturas de árvore para representar hierarquias de objetos parte-todo. Com o Composite, os clientes podem tratar objetos individuais e grupos de objetos de maneira uniforme, permitindo que sejam tratados de forma polimórfica.

Resumidamente, o padrão Composite consiste nos seguintes elementos:

1. Componente (Component): É uma interface ou classe abstrata que define a interface comum para todos os objetos na estrutura, tanto para objetos individuais como para composições. Ele declara operações que podem ser realizadas tanto nos objetos folha (individuais) quanto nos objetos compostos (grupos).
2. Objeto Folha (Leaf): É uma implementação concreta do Componente. Representa objetos individuais na estrutura, que não possuem filhos.
3. Objeto Composto (Composite): Também é uma implementação concreta do Componente, porém representa objetos que têm filhos. Ele armazena uma coleção de objetos Componente e implementa as operações definidas na interface Componente, repassando essas operações para seus filhos.

Ao tratar objetos folha e objetos compostos de forma uniforme, o padrão Composite permite a construção de estruturas complexas em que os clientes podem interagir com os objetos da mesma maneira, independentemente de serem objetos individuais ou grupos de objetos.

```typescript
abstract class FileSystemElement {
  constructor(protected name: string) {}

  abstract getSize(): number;

  abstract print(indentation: string): void;
}

class File extends FileSystemElement {
  constructor(name: string, private size: number) {
    super(name);
  }

  getSize(): number {
    return this.size;
  }

  print(indentation: string): void {
    console.log(indentation + "- " + this.name + " (Size: " + this.size + " bytes)");
  }
}

class Directory extends FileSystemElement {
  private children: FileSystemElement[] = [];

  constructor(name: string) {
    super(name);
  }

  add(element: FileSystemElement): void {
    this.children.push(element);
  }

  remove(element: FileSystemElement): void {
    const index = this.children.indexOf(element);
    if (index > -1) {
      this.children.splice(index, 1);
    }
  }

  getSize(): number {
    let totalSize = 0;
    for (const child of this.children) {
      totalSize += child.getSize();
    }
    return totalSize;
  }

  print(indentation: string): void {
    console.log(indentation + "+ " + this.name + " (Size: " + this.getSize() + " bytes)");
    for (const child of this.children) {
      child.print(indentation + "  ");
    }
  }
}

// Uso do Composite
const root = new Directory("Root");

const documents = new Directory("Documents");
const file1 = new File("file1.txt", 100);
const file2 = new File("file2.txt", 200);
documents.add(file1);
documents.add(file2);

const pictures = new Directory("Pictures");
const file3 = new File("image1.jpg", 300);
const file4 = new File("image2.jpg", 400);
pictures.add(file3);
pictures.add(file4);

root.add(documents);
root.add(pictures);

root.print("");
```

No contexto do exemplo do sistema de arquivos, a classe `File` representa objetos folha no padrão Composite. Os objetos folha são elementos individuais que não têm filhos. No caso do sistema de arquivos, os objetos folha são os arquivos individuais.

A classe `Directory`, por sua vez, representa os objetos compostos, que podem conter outros objetos, sejam eles arquivos ou outros diretórios. Os objetos compostos têm a responsabilidade de gerenciar a coleção de seus filhos e fornecer operações comuns para interagir com eles.

Portanto, na implementação fornecida, a classe `File` é um exemplo de objeto folha, enquanto a classe `Directory` é um exemplo de objeto composto. Essa estrutura de classes permite que os objetos folha e compostos sejam tratados de maneira uniforme, facilitando a construção e manipulação de estruturas hierárquicas de sistemas de arquivos.

---
Próxima anotação: [[45 - Estilos Arquiteturais]]
#arquitetura-de-software #design-patterns
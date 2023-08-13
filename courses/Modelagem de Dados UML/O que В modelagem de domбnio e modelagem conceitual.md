# Modelagem de domínio
- **Domínio**: é a área de negócio observada.
- **Modelo de domínio**: é um modelo que descreve:
	- As entidades do domínio;
	- As inter-relações entre elas.
<table border="1">
	<tr>
		<td>
			<b>Nível</b>
		</td>
		<td>
			<b>Responsável</b>
		</td>
		<td>
			<b>Objetivo</b>
		</td>
	</tr>
	<tr>
		<td>
			<b>Conceitual</b> ou de análise (de negócio)
		</td>
		<td>
			Analista de negócio
		</td>
		<td>
			Descrever as entidades do domínio <b>(do negócio)</b> e suas inter-relações: <b>Independemente de SISTEMA</b>.
		</td>
	</tr>
	<tr>
		<td>
			<b>Conceitual</b> ou de análise (de sistema)
		</td>
		<td>
			Analista de sistemas
		</td>
		<td>
			Descrever as entidades do domínio <b>(do sistema)</b> e suas inter-relações: <b>Independemente de PARADIGMA E TECNOLOGIA</b>.
		</td>
	</tr>
	<tr>
		<td>
			<b>Lógico</b> ou de design
		</td>
		<td>
			Projetista
		</td>
		<td>
			Descrever as entidades do domínio <b>(do sistema)</b> e suas inter-relações: <b>Preso a um PARADIGMA (ex: relacional, orientado a objeto); Independetemente de TECNOLOGIA</b>.
		</td>
	</tr>
	<tr>
		<td>
			<b>Físico</b> ou de implementação
		</td>
		<td>
			Implementador ou codificador
		</td>
		<td>
			Descrever as entidades do domínio <b>(do sistema)</b> e suas inter-relações: <b>Preso a um PARADIGMA (ex: relacional, orientado a objeto); Preso a uma TECNOLOGIA (ex: Java, C#, PHP, Python, Ruby e NodeJs)</b>.
		</td>
	</tr>
</table>
![[Pasted image 20220822204927.png]]
![[Pasted image 20220822205012.png]]
![[Pasted image 20220822205147.png]]
![[Pasted image 20220822205238.png]]
*`Paradigma orientado a objeto possui operações, ao contrário do estruturado e relacional.`*
![[Pasted image 20220822205408.png]]
![[Pasted image 20220822205450.png]]

---
# Polémica sobre análise & design
- **Análise**: descrever o PROBLEMA (independente de paradigma e tecnologia)
- **Design**: descrever a SOLUÇÃO (preso ao paradigma)

*Por que as disciplinas estão juntas no processo unificado?*

* Análise e Design tendem a ser mais próximas no desenvolvimento ao orientado ao objeto.
	* O processo de análise praticamente já vai produzir o que é necessário do projeto orientado a objeto, porém sem as operações.

---
#modelagem-de-dados-uml

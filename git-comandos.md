# Alguns comandos utilizados na aula.

> Para estruturar o nosso repositório, utilizei branches para indicar cada dia. Aqui comentarei qual foi o fluxo.

---

## Branch develop
> Criamos a branch de develop para, a partir dela, dar push de cada aula e criar uma branch do dia seguinte. Para isso executamos: <br/>
<code>git checkout -b develop origin/master</code><br/>
<code>git push origin develop</code>

---

## Branch de cada aula
> A branch de cada aula é criada a partir da develop: <br/>
<code>git checkout -b {Aula do dia} origin/develop</code> <br/>
<code>git commit -m "{Aula do dia}" --allow-empty </code> <br/>
<code>git push origin {Aula do dia}</code> <br/>  
Ex: <br/>
<code>git checkout -b Aula1 origin/develop</code> <br/>
<code>git commit -m "Aula1 - Preprocessadores" --allow-empty </code> <br/>
<code>git push origin Aula1</code> <br/>  

---

## Passando a branch do dia para a develop <br/>
<code> git rebase -i origin/develop </code><br/>
<code> git push -f origin {Aula do dia} </code><br/>
Criar Pull Request para a develop.


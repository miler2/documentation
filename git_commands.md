[*Go back to the index*](README.md)  

# Commands for Git

## Visualize log

Este comando nos muestra el historial de cambios realizados en el branch actual.

```
git log
```

Esto nos muestra el historial de cambios realizados en el branch actual de una forma más legible (solo en una línea). 

```
git log --oneline
```

Este comando muestra todos los cambios en una forma más visual sobre todas las ramas.

```
git log --all --graph
```


## Undoing things

### <ins>Checkout commit</ins>

Mostrar cómo estaba un commit específico sin hacer cambios.

```
git checkout [id_commit]
```

*Para volver al estado actual y seguir haciendo cambios:*

```
git checkout [nombre_branch] 
```


### <ins>Revert commit</ins>

Revertir un commit cualquiera, y hacer como si no se hubiera hecho ese commit. 

```
git revert [id_commit_a_eliminar]
```


### <ins>Reset commit</ins>

**ATENCION**: Cuidado con usar este comando, porque cuando se ejecute, ya no hay vuelta atrás, se perderán todos los commits posteriores al que hemos elegido volver.

Volver a un commit anterior y eliminar los commits que se hicieron después del que volvimos.

 

Usar opción **--hard** si queremos eliminar los cambios incluso en nuestros archivos dentro del editor. 

 
```
git reset [id_commit] --hard 
```


## Creating branches

Este comando nos crea un branch nuevo. 

```
git branch [nombre_branch] 
```



Este comando muestra los branches que tenemos, tanto en local, como en remoto. 

*-a: Esta opción nos pide mostrar todos los branches, incluyendo los remotos.*

```
git branch –a 
```


Este comando nos crea la rama y nos mete dentro de ella para empezar a hacer cambios.

*checkout: Indica que queremos ir a esa rama (no existe la rama ahora mismo).*

*-b: Como no existe la rama, esta opción la crea.*

```
git checkout –b [nombre_branch] 
```


Este comando elimina una rama.

```
git branch –D [nombre_branch] 
```

*-D: Elimina una rama.*


## Merging branches 

 

Si queremos añadir nuestros cambios de un branch <ins>[branch-a]</ins> a nuestro branch principal <ins>[main]</ins>, lo que tenemos que hacer es irnos a la rama a la que queremos añadir todos los cambios <ins>[main]</ins>, y luego ejecutar el comando merge con el nombre del branch que le queremos añadir:  

```
git merge [branch-a]
```

Si hay conflictos porque el archivo al que se le quiere hacer el merge <ins>[main]</ins> tiene unos cambios que nosotros no teníamos en nuestro branch <ins>[branch-a]</ins>, entonces tendremos que decirle al archivo qué cambios queremos mantener, y cuáles no (qué quiere mantener/quitar del branch <ins>[main]</ins> y qué quiere mantener/quitar del branch <ins>[branch-a]</ins>). Probablemente nos mostrará en la consola un archivo con el editor vim. Para salir de vim tendremos que escribir ":wq", esto nos guarda el archivo (w), y nos saca de éste (q). 

Después de hacer esto, tendremos que hacer un commit de nuevo. 

___
[*Go back to the index*](README.md) 
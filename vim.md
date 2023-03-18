* SOURCES: 
* * https://phoenixnap.com/kb/vim-commands-cheat-sheet
* * vimtutor is better than man pages
=   =   =   =   =   =   =   =   =   =   =   =   =   =   =   =   =   =   =   =   =   =   =   =   =
1) Movimiento dentro de un Archivo
1.1) Movimiento por Caracteres, Palabras, Tokens
    - Por caracteres:

              k 
           <h   l>
              j

    - Puedes utilizar estas keys con un prefijo numérico
            5j mueve el cursor 5 líneas abajo.

    - Palabras y Tókens
        b - mover el cursor al inicio de una palabra
        B - ..  ..  ..  ..  al inicio de un token
        w - ..  ..  ..  ..  al inicio de la siguiente palabra
        W - ..  ..  ..  ..  al inicio del siguiente token
        e - ..  ..  ..  ..  al final de una palabra
        E - ..  ..  ..  ..  al final de un token

1.2) Movimiento por Líneas
    0 - salta al principio de la línea
    $ - salta al final de la línea
    ^ - salta al primer caracter (no blanco) de la línea
    #G / #gg / :# - salta a la línea #

1.3) Movimiento por Screens
    Ctrl+b - retrocede una página
    Ctrl+f - avanza una página
    Ctrl+d - avanza media página
    Ctrl+u - retrocede media página
    Ctrl+e - mueve la página una línea más abajo
    Ctrl+y - mueve la página una linea más arriba
    Ctrl+o - retroceder en la jump histroy
    Ctrl+i - avanzar en la jump history
    H - Se mueve a lo más arriba de la screen (High)
    M - ..  ..   al medio de la screen (Middle)
    L - ..  ..   a lo más abajo de la screen (Low)

2) Insertando Texto
    i - cambiar a <<insert mode>> justo antes del cursor 
    I - insertar texto al inicio de la línea
    a - cambiar a <<insert mode>> despues del cursor
    A - insertar texto al final de una línea
    o - open a new line below the current one
    O - open a new line above the current one 
    ea - insertar texto al final de una palabra
    Esc - salir del <<insert mode>>

3) Editando texto
    r - reemplazar un solo caracter
    cc - reemplazar una línea entera (limpiar y abrir <<insert mode>>)
    C / c$ - reemplazar desde el cursor hasta el final de una línea
    cw - reemplazar desde el cursor hasta el final de una palabra
    s - eliminar un caracter y entrar a <<insert mode>>
    J - merge the line below to the current one with a space in between them
    gJ - .. ..  ..  ..  ..  ..  ..  ..  ..  ..  without a space in between them
    u - deshacer undo
    Crtl+r - rehacer redo
    . - repetir el comando pasado

3.1) Cortar, Copiar y Pegar
    yy - copiar la línea entera
    #yy - copiar líneas
    dd - eliminar la línea entera
    #dd - eliminar líneas
    p - pegar después del cursor
    P - pegar antes del cursor

4) Marcando Texto y <<visual mode>>
    v - selecionar texto en <<character mode>>
    V - selecionar el texto en <<line mode>>
    Ctrl+v - seleccionar el texto usando <<block mode>>
    o - moverse de un extremo del texto seleccionado al otro extremo
    aw - seleccionar una palabra
    ab - .. ..  un bloque con ()
    aB - .. ..  con {}
    at - .. ..  con <>
    ib - seleccionar un bloque interno de ()
    iB - .. ..  de {}
    it - .. ..  de <>

4.1) Visual Commands
    y - yank (copiar) el texto marcado
    d - delete ..
    p - paste after the cursor
    u - cambiar a lowercase
    U - cambiar a UPPERCASE

5) Buscar en el archivo
    /pattern - busca hacia delante por un patrón regex específico
    ?pattern - busca hacia atrás por un patrón regex especificado
    * - salta a la siguiente instancia de la palabra actual
    # - salta a la instancia anterior .. .. 
    n - repite la búsqueda en la mímsa dirección
    N - repite la búsqueda en la dirección opuesta

6) Guardar y Salir de un archivo
    :w - guardar el archivo
    :wq / :x / ZZ - guardar y salir del archivo
    :q - quit
    :q! / ZQ - quit sin guardar cambios
    :w nombre_archivo_nuevo - guarda el archivo con un nombre específico y continua editando el
                              original
    :sav - guarda el archivo como un nuevo archivo y continua editando la copia
    :w !sudo tee % - write out the file using sudo and tee command

7) Trabajando en múltiples archivos
    :e file_name  – open a file in a new buffer
    :bn  – move to the next buffer
    :bp – go back to previous buffer
    :bd  – close buffer
    :b#  – move to the specified buffer (by number)
    :b file_name – move to a buffer (by name)
    :ls – list all open buffers
    :sp file_name  – open a file in a new buffer and split viewport horizontally
    :vs file_name  – open a file in a new buffer and split viewport vertically
    :vert ba  – edit all files as vertical viewports
    :tab ba  – edit all buffers as tabs
    gt – move to next tab
    gT – move to previous tab
    Ctrl+ws – split viewport
    Ctrl+wv – split viewport vertically
    Ctrl+ww – switch viewports
    Ctrl+wq – quit a viewport
    Ctrl+wx – exchange current viewport with next one
    Ctrl+= – make all viewports equal in height and width

8) Marks and Jumps
    m[a-z] – mark text using character mode (from a to z)
    M[a-z] – mark lines using line mode (from a to z)
    `a - jump to position marked a
    `y`a – yank text to position marked >a>
    `. – jump to last change in file
    `0 – jump to position where Vim was last exited
    `` – jump to last jump
    :marks – list all marks
    :jumps – list all jumps
    :changes – list all changes
    Ctrl+i – move to next instance in jump list
    Ctrl+o – move to previous instance in jump list
    g, – move to next instance in change list
    g; – move to previous instance in change list

9) Macros
    qa  – record macro a
    q  – stop recording macro
    @a  – run macro a
    @@  – run last macro again

10) Activando Vim Color Schemes
    :colorscheme [colorscheme_name]  – change to specified scheme
    :colorscheme [space]+Ctrl+d – list available Vim color scheme

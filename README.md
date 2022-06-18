# Settings Terminal for vim, bash, kubectl etc

## Bash
Добавить строки в файл: ~/.bashrc
```bash
export TZ=UTC
```


Альясы к командам.  
Добавить строки в файл: ~/.bash_aliass или ~/.bashrc
```bash
alias ll='ls -alF'                                                                                                                                     
alias la='ls -A'                                                                                                                                       
alias l='ls -CF'                                                                                                                                       
alias k=kubectl 
```


## Vim
Автонуменрация строк в редакторе, вид курсора в разных режимах.  
Добавить строки в файл: ~/.vim/vimrc или /etc/vim/vimrc
```bash
set number                                                                                                                                             
set ttimeoutlen=10 "Понижаем задержку ввода escape последовательностей
let &t_SI.="\e[5 q" "SI = режим вставки                                                                                                                
let &t_SR.="\e[3 q" "SR = режим замены                                                                                                      
let &t_EI.="\e[1 q" "EI = нормальный режим     
```


## Kubectl
Автодополнение команды kubectl.
Добавить строки в файл: ~./.bashrc
```bash
complete -F __start_kubectl k                                                                                                                          
source <(kubectl completion bash)  
```


## Helm
Автодополнение команд Helm.
```bash
source <(helm completion bash)
helm completion bash > /etc/bash_completion.d/helm
```


## Git
Короткий вывод приглашения и указание названия ветки текущей ветки репозитария.  
Добавить строки в файл: ~/.bashrc
```bash
. ~/git-prompt.sh                                                                                                                                      
export GIT_PS1_SHOWDIRTYSTATE=1                                                                                                                        
export PS1='\[\033[36m\]\w:$(__git_ps1 "\[\033[32m\](%s)")\[\033[34m\]$ \[\033[37m\]'
```
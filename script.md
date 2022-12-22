# Instalando zsh
sudo apt-get install zsh 

# Instalando oh-my-zsh
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

# Instalar o zsh-syntax-highlighting
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting


# Instalar o zsh-AutoSuggestion
git clone https://github.com/zsh-users/zsh-autosuggestions $ZSH_CUSTOM/plugins/zsh-autosuggestions

# Acrescentar no arquivo .zshrc
plugins=(
    git
    zsh-syntax-highlighting
    zsh-autosuggestions
)

##Instalando o tema Starship
curl -sS https://starship.rs/install.sh | sh

# Adicione ZSH_THEME="starship" nas configurações do ZSH
source ~/.zshrc

# incluir ao final do arquivo .zshrc
eval "$(starship init zsh)"
source ~/.zshrc

# Criar o arquivo de configuração do starship
mkdir -p ~/.config && touch ~/.config/starship.toml

# Colar o conteúdo no arquivo starship.toml

# Inserts a blank line between shell prompts
add_newline = true

# Customizing the prompt
format = """
$username\
$hostname\
$shlvl\
$singularity\
$kubernetes\
$directory\
$vcsh\
$git_branch\
$git_commit\
$git_state\
$git_metrics\
$git_status\
$hg_branch\
$docker_context\
$package\
$cmake\
$cobol\
$dart\
$deno\
$dotnet\
$elixir\
$elm\
$erlang\
$golang\
$helm\
$java\
$julia\
$kotlin\
$lua\
$nim\
$nodejs\
$ocaml\
$perl\
$php\
$pulumi\
$purescript\
$python\
$rlang\
$red\
$ruby\
$rust\
$scala\
$swift\
$terraform\
$vlang\
$vagrant\
$zig\
$nix_shell\
$conda\
$memory_usage\
$aws\
$gcloud\
$openstack\
$azure\
$env_var\
$crystal\
$custom\
$sudo\
$cmd_duration\
$line_break\
$jobs\
$battery\
$time\
$status\
$shell\
[$character](bold green)"""

# Configure if and how the time is shown
[time]
disabled = false
time_format = "%T"
format = "🕙[$time ](bold blue)"

[sudo]
disabled = false
style = "bold green"
symbol = "💪"
format = "[<SUDO>$symbol]($style)"

[status]
disabled = false
style = "bg:blue"
symbol = "🔴"
map_symbol = true
format = '[\[$symbol $common_meaning$signal_name$maybe_int\]]($style) '

source /home/ricmed/.zshrc 

## Instalar Nerd Font - RobotoMono Nerd Font
# Fazer o download de uma Nerd Font

# Unzip and copy
sudo unzip RobotoMono.zip -d /usr/share/fonts/truetype/RobotoMono

# Executar o comando abaixo para o rebuild do cache das fontes
fc-cache -fv

# Caso não encontre o comando fc-cache
sudo apt install fontconfig

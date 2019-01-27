# Tunes-Rank-Management
# The Skript for Tunes ranks

# Please do not claim this as your own

command /rank [<offline player>] [<text>]: # main command
	trigger:
		if player = "Lotix": # Only I can set player's ranks
			if arg-1 or arg-2 is not set:
				send "" to player
				send "&3&lTUNES &8⎜ &bRank Management" to player
				send "" to player
				send "&7&l* &b/rank <player> <rank>" to player
				send "&7&oSets a player's rank to the argument" to player
				send "&7&l* &b/rank <player> reset" to player
				send "&7&oResets a player's rank to default" to player
				send "&7&l* &b/rank <player> demote" to player
				send "&7&oDemotes a player to the rank below them"
				send "&7&l* &b/rank <player> promote" to player
				send "&7&oPromotes a player to the rank above them" to player
				send "&7&l* &b/rank <player> check" to player
				send "&7&oChecks a player's rank and sends it to you" to player
				send "" to player
			else if arg-1 and arg-2 is set:
				if arg-2 is "Reset":
					if {rank::%arg-1's uuid%} is "Default":
						send "&3&lRANKS &8⎜ &cThis player is already rank Default!" to player
						stop
					else:
						set {rank::%arg-1's UUID%} to "Default"
						send "&3&lRANKS &8⎜ &7You have reset &b%arg-1%'s rank &7to &bDefault!" to player
						send "&3&lRANKS &8⎜ &7Your rank has been reset back to Default!" to arg-1
						stop
				if arg-2 is "Promote":
					if {rank::%arg-1's uuid%} is "Default":
						set {rank::%arg-1's uuid%} to "Helper"
						send "&3&lRANKS &8⎜ &7You have promoted &b%arg-1%! %arg-1%'s &7rank is now &b%{rank::%arg-1's uuid%}%!" to player
						send "&3&lRANKS &8⎜ &7You have been promoted to &b%{rank::%arg-1's uuid%}%!" to arg-1
						stop
					if {rank::%arg-1's uuid%} is "Helper":
						set {rank::%arg-1's uuid%} to "Mod"
						send "&3&lRANKS &8⎜ &7You have promoted &b%arg-1%! %arg-1%'s &7rank is now &b%{rank::%arg-1's uuid%}%!" to player
						send "&3&lRANKS &8⎜ &7You have been promoted to &b%{rank::%arg-1's uuid%}%!" to arg-1
						stop
					if {rank::%arg-1's uuid%} is "Mod":
						set {rank::%arg-1's uuid%} to "Srmod"
						send "&3&lRANKS &8⎜ &7You have promoted &b%arg-1%! %arg-1%'s &7rank is now &b%{rank::%arg-1's uuid%}%!" to player
						send "&3&lRANKS &8⎜ &7You have been promoted to &b%{rank::%arg-1's uuid%}%!" to arg-1
						stop
					if {rank::%arg-1's uuid%} is "Srmod":
						set {rank::%arg-1's uuid%} to "Admin"
						send "&3&lRANKS &8⎜ &7You have promoted &b%arg-1%! %arg-1%'s &7rank is now &b%{rank::%arg-1's uuid%}%!" to player
						send "&3&lRANKS &8⎜ &7You have been promoted to &b%{rank::%arg-1's uuid%}%!" to arg-1
						stop
					if {rank::%arg-1's uuid%} is "Admin":
						set {rank::%arg-1's uuid%} to "Owner"
						send "&3&lRANKS &8⎜ &7You have promoted &b%arg-1%! %arg-1%'s &7rank is now &b%{rank::%arg-1's uuid%}%!" to player
						send "&3&lRANKS &8⎜ &7You have been promoted to &b%{rank::%arg-1's uuid%}%!" to arg-1
						stop
					if {rank::%arg-1's uuid%} is "Owner":
						send "&3&lRANKS &8⎜ &cYou cannot promote an Owner!" to player
						stop
				if arg-2 is "Demote":
					if {rank::%arg-1's uuid%} is "Default":
						send "&3&lRANKS &8⎜ &cYou cannot demote a default player!" to player
						stop
					if {rank::%arg-1's uuid%} is "Helper":
						set {rank::%arg-1's uuid%} to "Default"
						send "&3&lRANKS &8⎜ &7You have demoted &b%arg-1%! %arg-1%'s &7rank is now &b%{rank::%arg-1's uuid%}%!" to player
						send "&3&lRANKS &8⎜ &7You have been demoted to &b%{rank::%arg-1's uuid%}%!" to arg-1
						stop
					if {rank::%arg-1's uuid%} is "Mod":
						set {rank::%arg-1's uuid%} to "Helper"
						send "&3&lRANKS &8⎜ &7You have demoted &b%arg-1%! %arg-1%'s &7rank is now &b%{rank::%arg-1's uuid%}%!" to player
						send "&3&lRANKS &8⎜ &7You have been demoted to &b%{rank::%arg-1's uuid%}%!" to arg-1
						stop
					if {rank::%arg-1's uuid%} is "Srmod":
						set {rank::%arg-1's uuid%} to "Mod"
						send "&3&lRANKS &8⎜ &7You have demoted &b%arg-1%! %arg-1%'s &7rank is now &b%{rank::%arg-1's uuid%}%!" to player
						send "&3&lRANKS &8⎜ &7You have been demoted to &b%{rank::%arg-1's uuid%}%!" to arg-1
						stop
					if {rank::%arg-1's uuid%} is "Admin":
						set {rank::%arg-1's uuid%} to "Srmod"
						send "&3&lRANKS &8⎜ &7You have demoted &b%arg-1%! %arg-1%'s &7rank is now &b%{rank::%arg-1's uuid%}%!" to player
						send "&3&lRANKS &8⎜ &7You have been demoted to &b%{rank::%arg-1's uuid%}%!" to arg-1
						stop
					if {rank::%arg-1's uuid%} is "Owner":
						set {rank::%arg-1's uuid%} to "Admin"
						send "&3&lRANKS &8⎜ &7You have demoted &b%arg-1%! %arg-1%'s &7rank is now &b%{rank::%arg-1's uuid%}%!" to player
						send "&3&lRANKS &8⎜ &7You have been demoted to &b%{rank::%arg-1's uuid%}%!" to arg-1
						stop
				if arg-2 is "Check":
					send "&3&lRANKS &8⎜ &b%arg-1%'s &7is currently rank &b%{rank::%arg-1's uuid%}%!" to player
					stop
				if arg-2 is "Owner" or "Admin" or "Srmod" or "Mod" or "Helper" or "Builder" or "Partner" or "Media" or "Miner":
					set {rank::%arg-1's UUID%} to arg-2
					send "&3&lRANKS &8⎜ &7You have set &b%arg-1% &7to the &b%arg-2% rank!" to player
					send "&3&lRANKS &8⎜ &7You are now a &b%arg-2% rank!" to arg-1
				if arg-2 is not "Owner" or "Admin" or "Srmod" or "Mod" or "Helper" or "Builder" or "Partner" or "Media" or "Miner":
					send "&3&lRANKS &8⎜ &cAn error occured while performing this action!" to player
		else:
			send "&3&lRANKS &8⎜ &cYou cannot perform this action!" to player 

on first join:
    set {rank::%player's uuid%} to "Default"

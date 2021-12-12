
<!-- Модуль 2
	 (2::8) Лекция 14. Типобезопасность SLTC: сохранение -->

# Simply Typed Lambda Calculus (SLTC) #

Вспомогательные леммы про переставноку и ослабление.


## Лемма о сохранении подстановки ##	

Если $\Gamma, x{:}S \vdash t : T$ и $\Gamma \vdash s : S$,
то $\Gamma \vdash [s/x]t : T$.


## Теорема о сохранении ##

Если $\Gamma \vdash t : T$ и $t \longrightarrow t'$,
то $\Gamma \vdash t' : T$

#### Доказательство ####

1.	Правило T-App:  
	$\cfrac{\Gamma \vdash t_1 : T_1 \rightarrow T_2
	\quad \Gamma \vdash t_2 : T_1}
	{\Gamma \vdash t_1\ t_2 : T_2}$
	
	Возможны несколько правил вычисления:
	
	1.	Правило E-App1:  
		$\cfrac{t_1 \longrightarrow t_1'}{t_1\ t_2 \longrightarrow t_1'\ t_2}$
		Для `t1` выполняется индуктивная гипотеза, поэтому `t1' : T1 -> T2`.
		
	2.	Правило E-Abs:  
		$\cfrac{}{(\lambda x. t_1)\ v_2 \longrightarrow [v_2 / x]t_1}$  
		Применяем лемму о сохранении типов при подстановке.	


## Завершимость вычислений ##

Вычисление всех правильно типизированных термов в STLC завершается.

Каждый шаг вычисления уменьшает некоторую меру терма. Какая это мера?  
_Размер_ не подходит, размер увеличивается. Например,  
$(\lambda x. f x x) t$, где `|t| = 10`.  
У исходного терма размер 1 + 2 + 3 + 10 (16), а у нового 2 + 1 + 20.

А есть ли другой показатель, который уменьшается? 
_Глубина_ тоже может увеличиваться, значт тоже не подходит. 



## Задания ##


## Литература ##

*	Бенджамин Пирс, глава 9 (SLTC).
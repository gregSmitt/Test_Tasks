1. Код выводит:
Bad: undefined
Bad: undefined
Bad: undefined
Bad: undefined

2. Варианты модификаций (с учетом того, что нужно вывести значения именно через 3 секунды):
А. Заменить var на let
const arr = [10, 12, 15, 21]

for (let i = 0; i < arr.length; i++) {
	setTimeout(() => {
		console.log(arr[i] > 13 ? `Good: ${arr[i]}` : `Bad: ${arr[i]}`)
	}, 3000)
}

B. Вызывать в теле цикла функцию, которая принимает текущее значение i в качестве аргумента, 
и уже с использованием новой пременной вызывает тот же setTimeout

const arr = [10, 12, 15, 21]

function cantLiveWithoutVar(i) {
	setTimeout(() => {
		console.log(arr[i] > 13 ? `Good: ${arr[i]}` : `Bad: ${arr[i]}`)
	}, 3000)
}

for (var i = 0; i < arr.length; i++) {
	cantLiveWithoutVar(i)
}

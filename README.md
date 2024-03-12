```
// Сортировка массива с помощью замыкания
var nums = [1,2,4,1,7,8,12,1,2,4]

let sortedNamesForward = nums.sorted { $0 < $1 }
print("Отсортированный массив в одну сторону: \(sortedNamesForward)")

let sortedNamesBackward = nums.sorted { $0 > $1 }
print("Отсортированный массив в обратную сторону: \(sortedNamesBackward)")

// Метод для сортировки имен друзей по количеству букв и создания словаря
func sortNamesAndCreateDictionary(_ friendsNames: [String]) -> [Int: [String]] {
    let sortedNames = friendsNames.sorted { $0.count < $1.count }
    var namesDictionary = [Int: [String]]()

    for name in sortedNames {
        let length = name.count
        if namesDictionary[length] == nil {
            namesDictionary[length] = [name]
        } else {
            namesDictionary[length]?.append(name)
        }
    }

    return namesDictionary
}

let friends = ["Денис", "Елена", "Александр", "Ирина", "Николай"]
let sortedNamesDictionary = sortNamesAndCreateDictionary(friends)
print("Словарь с именами друзей: \(sortedNamesDictionary)")

// Функция для вывода ключа и значения из словаря
func printKeyValue<Key, Value>(_ key: Key, _ value: Value) {
    print("Ключ: \(key), Значение: \(value)")
}

// Пример использования функции
if let firstKey = sortedNamesDictionary.keys.first,
   let firstValue = sortedNamesDictionary[firstKey]?.first {
    printKeyValue(firstKey, firstValue)
}

// Функция для проверки массивов на пустоту и вывода в консоль
func checkAndPrintArrays<T, U>(_ stringArray: [T], _ numericArray: [U]) {
    if stringArray.isEmpty {
        print("Строковый массив пуст, добавляем значение...")
        // Добавляем произвольное значение
        // stringArray.append("Пример")
    }

    if numericArray.isEmpty {
        print("Числовой массив пуст, добавляем значение...")
        // Добавляем произвольное значение
        // numericArray.append(123)
    }

    print("Строковый массив: \(stringArray)")
    print("Числовой массив: \(numericArray)")
}

// Пример использования функции
let emptyStringArray: [String] = []
let emptyNumericArray: [Int] = []
checkAndPrintArrays(emptyStringArray, emptyNumericArray)

```
![изображение](https://github.com/vihuhool/swifty2/assets/69204363/5bb649be-a1cb-49da-837d-1bf35855fc7b)
![изображение](https://github.com/vihuhool/swifty2/assets/69204363/28f50707-aab5-467b-ac0d-30ba4251d323)


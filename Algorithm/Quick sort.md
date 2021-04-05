기준 원소를 하나 정하고(가장 왼쪽, 중간, 가장 오른쪽 등) 기준값보다 작다면 왼쪽, 크다면 오른쪽으로 배열을 재배치 한다.

빠른 편에 속하는 mergesort보다 평균적으로는 2배정도 빠르다. 대신 코드 구현이 어려운축에 속한다.

또 운이 나쁘면 느리다는 단점과 같은 숫자들을 정렬할 경우 순서가 섞일 가능성이 있다는 단점이 있다.

```jsx
function quickSort (array, left = 0, right = array.length - 1) {
if (left >= right) {
return;
}
const mid = Math.floor((left + right) / 2);
const pivot = array[mid];
const partition = divide(array, left, right, pivot);
quickSort(array, left, partition - 1);
quickSort(array, partition, right);
function divide (array, left, right, pivot) {
console.log(`array: ${array}, left: ${array[left]}, pivot: ${pivot}, right: ${array[right]}`)
while (left <= right) {
while (array[left] < pivot) {
left++;
}
while (array[right] > pivot) {
right--;
}
if (left <= right) {
let swap = array[left];
array[left] = array[right];
array[right] = swap;
left++;
right--;
}
}
return left;
}
return array;
}

출처: https://im-developer.tistory.com/135 [Code Playground]
```

배열의 왼쪽 인덱스는 0, 오른쪽인덱스는 length -1로 설정한다.

중간의 피벗값을 구해서 partition으로 설정할 인덱스를 리턴받는다.

그리고 재귀를 돌려서 left의 값과 right의 값들을 정렬한다.

### big O

퀵정렬은 대부분의 경우 매우 좋은 성능을 보여준다고 한다. 최선의 경우에는 nlogn의 시간 복잡도를 가지게 되고 최악의 경우에는 n^2의 시간 복잡도를 가지게 된다.

최악의 경우는 이미 정렬된 배열의 첫번째 요소를 기준값으로 하게 되는 경우가 된다. 재귀를 배열의 길이만큼 호출하기 때문에 효율적이라고 볼 수 없다.

그렇지만 이런 경우가 아닌 일반적인 경우라면 nlogn의 시간복잡도를 가지게 되기 때문에 많이 쓰이는 정렬이다.

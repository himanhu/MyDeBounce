# MyDeBounce
<--------- Global Debounce Function ----->

export default function debounce(func, wait) {
  let timeoutID = null;
  return function(...args){
    const context = this;
    clearTimeout(timeoutID);
     timeoutID = setTimeout(function () {
      timeoutID = null; // Not strictly necessary but good to do this.
      func.apply(context, args);
    }, wait);
  }

}

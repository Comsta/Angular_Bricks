# Angular_Bricks
useful Angular bricks

```javascript
/**
 * Drop Down diredctive
 * useful in easily building DropDown Menus
 */
Directive({
	selector: '[myDropdown]'
})
export class DropdownDirective {
	private isOpen: boolean = false;

	@HostBinding('class.open')
	get _opened() {
		return this.isOpen;
	}

	@HostListener('click') open() {
		this.isOpen = !this.isOpen;
	}

	@HostListener('mouseleave') close() {
		this.isOpen = false;
	}
}
```

Get class on Mouse event
``` javascript
 @HostListener('mousemove', ['$event']) onMouseMove(event: MouseEvent) {
    const eventSource = (window.event) ? event.srcElement.className : (<Element>event.target).className;
 ..
```

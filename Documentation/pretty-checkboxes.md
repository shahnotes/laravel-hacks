# Pretty Checkboxes

### Implementing pretty checkboxes

##### Step 1: Add this HTML code

```HTML
<label class="k-checkbox k-checkbox--single k-checkbox--solid">
    <input type="checkbox" value="" class="k-checkable">
    <span></span>
</label>
```

##### Step 2: Add this css rules

```CSS
.k-checkbox {
  display: inline-block;
  position: relative;
  padding-left: 30px;
  margin-bottom: 10px;
  text-align: left;
  cursor: pointer;
  font-size: 1rem;
  -webkit-transition: all 0.3s ease;
  transition: all 0.3s ease; }
  .k-checkbox.k-checkbox--disabled {
    opacity: 0.8;
    cursor: not-allowed; }
  .k-checkbox > input {
    position: absolute;
    z-index: -1;
    opacity: 0; }
  .k-checkbox > span {
    border-radius: 3px;
    background: none;
    position: absolute;
    top: 1px;
    left: 0;
    height: 23px;
    width: 23px; }
    .k-checkbox > span:after {
      content: '';
      position: absolute;
      display: none;
      top: 50%;
      left: 50%;
      margin-left: -3px;
      margin-top: -8px;
      width: 6px;
      height: 14px;
      color: black;
      border-width: 0 2px 2px 0/*rtl:ignore*/ !important;
      -webkit-transform: rotate(45deg)/*rtl:ignore*/;
      transform: rotate(45deg)/*rtl:ignore*/; }
  .k-checkbox > input:checked ~ span {
    -webkit-transition: all 0.3s ease;
    transition: all 0.3s ease;
    background: none; }
    .k-checkbox > input:checked ~ span:after {
      display: block; }
  .k-checkbox:hover > input:not([disabled]):checked ~ span,
  .k-checkbox > input:checked ~ span {
    -webkit-transition: all 0.3s ease;
    transition: all 0.3s ease; }
  .k-checkbox > input:disabled ~ span {
    opacity: 0.6;
    pointer-events: none; }
  .k-checkbox.k-checkbox--solid > span {
    border: 1px solid transparent; }
  .k-checkbox.k-checkbox--solid:hover > input:not([disabled]) ~ span,
  .k-checkbox.k-checkbox--solid > input:focus ~ span {
    -webkit-transition: all 0.3s ease;
    transition: all 0.3s ease; }
  .k-checkbox.k-checkbox--square > span {
    border-radius: 0; }
  .k-checkbox.k-checkbox--bold > span {
    border-width: 2px !important;
    -webkit-transition: all 0.3s ease;
    transition: all 0.3s ease; }
  .form-inline .k-checkbox {
    margin-left: 15px;
    margin-right: 15px; }
  .k-checkbox.k-checkbox--single {
    width: 18px;
    height: 18px; }
    .k-checkbox.k-checkbox--single > span {
      top: 0px; }
    th > .k-checkbox.k-checkbox--single,
    td > .k-checkbox.k-checkbox--single {
      right: -5px; }
  .input-group .k-checkbox {
    margin-bottom: 0 !important;
    padding-left: 0; }

.k-checkbox-list {
  padding: 0 0; }
  .form-horizontal .form-group .k-checkbox-list {
    padding-top: 0; }
  .k-checkbox-list .k-checkbox {
    text-align: left;
    display: block; }
    .k-checkbox-list .k-checkbox:last-child {
      margin-bottom: 5px; }

.k-checkbox-inline {
  padding: 0 0; }
  .k-checkbox-inline .k-checkbox {
    display: inline-block;
    margin-right: 15px;
    margin-bottom: 5px; }
    .k-checkbox-inline .k-checkbox:last-child {
      margin-right: 0; }

.form-group.row .k-checkbox-inline {
  margin-top: 0.75rem; }

.form-group.row .k-checkbox-list {
  margin-top: 2px; }

.k-checkbox.k-checkbox--disabled {
  opacity: 0.7; }

.k-checkbox > span {
  border: 1px solid #c9cedc; }
  .k-checkbox > span:after {
    border: solid #bac0d2; }

.k-checkbox > input:disabled ~ span:after {
  border-color: #c0c6d6; }

.k-checkbox > input:checked ~ span {
  border: 1px solid #c0c6d6; }

.k-checkbox.k-checkbox--bold > input:checked ~ span {
  border: 2px solid #c0c6d6; }

.k-checkbox > input:disabled ~ span {
  opacity: 0.6; }

.k-checkbox.k-checkbox--solid > span {
  background: transparent;
  border: 1px solid black !important; }
  .k-checkbox.k-checkbox--solid > span:after {
    border: solid black; }

.k-checkbox.k-checkbox--solid > input:focus ~ span {
  border: 1px solid black !important; }

.k-checkbox.k-checkbox--solid > input:checked ~ span {
  background: transparent; }

.k-checkbox.k-checkbox--brand.k-checkbox--disabled {
  opacity: 0.7; }

.k-checkbox.k-checkbox--brand > span {
  border: 1px solid #5c4de5; }
  .k-checkbox.k-checkbox--brand > span:after {
    border: solid #5c4de5; }

.k-checkbox.k-checkbox--brand > input:disabled ~ span:after {
  border-color: #5c4de5; }

.k-checkbox.k-checkbox--brand > input:checked ~ span {
  border: 1px solid #5c4de5; }

.k-checkbox.k-checkbox--brand.k-checkbox--bold > input:checked ~ span {
  border: 2px solid #5c4de5; }

.k-checkbox.k-checkbox--brand > input:disabled ~ span {
  opacity: 0.6; }

.k-checkbox.k-checkbox--brand.k-checkbox--solid > span {
  background: #5c4de5;
  border: 1px solid transparent !important; }
  .k-checkbox.k-checkbox--brand.k-checkbox--solid > span:after {
    border: solid #ffffff; }

.k-checkbox.k-checkbox--brand.k-checkbox--solid > input:focus ~ span {
  border: 1px solid transparent !important; }

.k-checkbox.k-checkbox--brand.k-checkbox--solid > input:checked ~ span {
  background: #5c4de5; }

.k-checkbox.k-checkbox--metal.k-checkbox--disabled {
  opacity: 0.7; }

.k-checkbox.k-checkbox--metal > span {
  border: 1px solid #dfe4ec; }
  .k-checkbox.k-checkbox--metal > span:after {
    border: solid #dfe4ec; }

.k-checkbox.k-checkbox--metal > input:disabled ~ span:after {
  border-color: #dfe4ec; }

.k-checkbox.k-checkbox--metal > input:checked ~ span {
  border: 1px solid #dfe4ec; }

.k-checkbox.k-checkbox--metal.k-checkbox--bold > input:checked ~ span {
  border: 2px solid #dfe4ec; }

.k-checkbox.k-checkbox--metal > input:disabled ~ span {
  opacity: 0.6; }

.k-checkbox.k-checkbox--metal.k-checkbox--solid > span {
  background: #dfe4ec;
  border: 1px solid transparent !important; }
  .k-checkbox.k-checkbox--metal.k-checkbox--solid > span:after {
    border: solid #67707e; }

.k-checkbox.k-checkbox--metal.k-checkbox--solid > input:focus ~ span {
  border: 1px solid transparent !important; }

.k-checkbox.k-checkbox--metal.k-checkbox--solid > input:checked ~ span {
  background: #dfe4ec; }

.k-checkbox.k-checkbox--light.k-checkbox--disabled {
  opacity: 0.7; }

.k-checkbox.k-checkbox--light > span {
  border: 1px solid #ffffff; }
  .k-checkbox.k-checkbox--light > span:after {
    border: solid #ffffff; }

.k-checkbox.k-checkbox--light > input:disabled ~ span:after {
  border-color: #ffffff; }

.k-checkbox.k-checkbox--light > input:checked ~ span {
  border: 1px solid #ffffff; }

.k-checkbox.k-checkbox--light.k-checkbox--bold > input:checked ~ span {
  border: 2px solid #ffffff; }

.k-checkbox.k-checkbox--light > input:disabled ~ span {
  opacity: 0.6; }

.k-checkbox.k-checkbox--light.k-checkbox--solid > span {
  background: #ffffff;
  border: 1px solid transparent !important; }
  .k-checkbox.k-checkbox--light.k-checkbox--solid > span:after {
    border: solid #282a3c; }

.k-checkbox.k-checkbox--light.k-checkbox--solid > input:focus ~ span {
  border: 1px solid transparent !important; }

.k-checkbox.k-checkbox--light.k-checkbox--solid > input:checked ~ span {
  background: #ffffff; }

.k-checkbox.k-checkbox--dark.k-checkbox--disabled {
  opacity: 0.7; }

.k-checkbox.k-checkbox--dark > span {
  border: 1px solid #645ca1; }
  .k-checkbox.k-checkbox--dark > span:after {
    border: solid #645ca1; }

.k-checkbox.k-checkbox--dark > input:disabled ~ span:after {
  border-color: #645ca1; }

.k-checkbox.k-checkbox--dark > input:checked ~ span {
  border: 1px solid #645ca1; }

.k-checkbox.k-checkbox--dark.k-checkbox--bold > input:checked ~ span {
  border: 2px solid #645ca1; }

.k-checkbox.k-checkbox--dark > input:disabled ~ span {
  opacity: 0.6; }

.k-checkbox.k-checkbox--dark.k-checkbox--solid > span {
  background: #645ca1;
  border: 1px solid transparent !important; }
  .k-checkbox.k-checkbox--dark.k-checkbox--solid > span:after {
    border: solid #ffffff; }

.k-checkbox.k-checkbox--dark.k-checkbox--solid > input:focus ~ span {
  border: 1px solid transparent !important; }

.k-checkbox.k-checkbox--dark.k-checkbox--solid > input:checked ~ span {
  background: #645ca1; }

.k-checkbox.k-checkbox--accent.k-checkbox--disabled {
  opacity: 0.7; }

.k-checkbox.k-checkbox--accent > span {
  border: 1px solid #00c5dc; }
  .k-checkbox.k-checkbox--accent > span:after {
    border: solid #00c5dc; }

.k-checkbox.k-checkbox--accent > input:disabled ~ span:after {
  border-color: #00c5dc; }

.k-checkbox.k-checkbox--accent > input:checked ~ span {
  border: 1px solid #00c5dc; }

.k-checkbox.k-checkbox--accent.k-checkbox--bold > input:checked ~ span {
  border: 2px solid #00c5dc; }

.k-checkbox.k-checkbox--accent > input:disabled ~ span {
  opacity: 0.6; }

.k-checkbox.k-checkbox--accent.k-checkbox--solid > span {
  background: #00c5dc;
  border: 1px solid transparent !important; }
  .k-checkbox.k-checkbox--accent.k-checkbox--solid > span:after {
    border: solid #ffffff; }

.k-checkbox.k-checkbox--accent.k-checkbox--solid > input:focus ~ span {
  border: 1px solid transparent !important; }

.k-checkbox.k-checkbox--accent.k-checkbox--solid > input:checked ~ span {
  background: #00c5dc; }

.k-checkbox.k-checkbox--focus.k-checkbox--disabled {
  opacity: 0.7; }

.k-checkbox.k-checkbox--focus > span {
  border: 1px solid #9816f4; }
  .k-checkbox.k-checkbox--focus > span:after {
    border: solid #9816f4; }

.k-checkbox.k-checkbox--focus > input:disabled ~ span:after {
  border-color: #9816f4; }

.k-checkbox.k-checkbox--focus > input:checked ~ span {
  border: 1px solid #9816f4; }

.k-checkbox.k-checkbox--focus.k-checkbox--bold > input:checked ~ span {
  border: 2px solid #9816f4; }

.k-checkbox.k-checkbox--focus > input:disabled ~ span {
  opacity: 0.6; }

.k-checkbox.k-checkbox--focus.k-checkbox--solid > span {
  background: #9816f4;
  border: 1px solid transparent !important; }
  .k-checkbox.k-checkbox--focus.k-checkbox--solid > span:after {
    border: solid #ffffff; }

.k-checkbox.k-checkbox--focus.k-checkbox--solid > input:focus ~ span {
  border: 1px solid transparent !important; }

.k-checkbox.k-checkbox--focus.k-checkbox--solid > input:checked ~ span {
  background: #9816f4; }

.k-checkbox.k-checkbox--primary.k-checkbox--disabled {
  opacity: 0.7; }

.k-checkbox.k-checkbox--primary > span {
  border: 1px solid #5867dd; }
  .k-checkbox.k-checkbox--primary > span:after {
    border: solid #5867dd; }

.k-checkbox.k-checkbox--primary > input:disabled ~ span:after {
  border-color: #5867dd; }

.k-checkbox.k-checkbox--primary > input:checked ~ span {
  border: 1px solid #5867dd; }

.k-checkbox.k-checkbox--primary.k-checkbox--bold > input:checked ~ span {
  border: 2px solid #5867dd; }

.k-checkbox.k-checkbox--primary > input:disabled ~ span {
  opacity: 0.6; }

.k-checkbox.k-checkbox--primary.k-checkbox--solid > span {
  background: #5867dd;
  border: 1px solid transparent !important; }
  .k-checkbox.k-checkbox--primary.k-checkbox--solid > span:after {
    border: solid #ffffff; }

.k-checkbox.k-checkbox--primary.k-checkbox--solid > input:focus ~ span {
  border: 1px solid transparent !important; }

.k-checkbox.k-checkbox--primary.k-checkbox--solid > input:checked ~ span {
  background: #5867dd; }

.k-checkbox.k-checkbox--success.k-checkbox--disabled {
  opacity: 0.7; }

.k-checkbox.k-checkbox--success > span {
  border: 1px solid #1dc9b7; }
  .k-checkbox.k-checkbox--success > span:after {
    border: solid #1dc9b7; }

.k-checkbox.k-checkbox--success > input:disabled ~ span:after {
  border-color: #1dc9b7; }

.k-checkbox.k-checkbox--success > input:checked ~ span {
  border: 1px solid #1dc9b7; }

.k-checkbox.k-checkbox--success.k-checkbox--bold > input:checked ~ span {
  border: 2px solid #1dc9b7; }

.k-checkbox.k-checkbox--success > input:disabled ~ span {
  opacity: 0.6; }

.k-checkbox.k-checkbox--success.k-checkbox--solid > span {
  background: #1dc9b7;
  border: 1px solid transparent !important; }
  .k-checkbox.k-checkbox--success.k-checkbox--solid > span:after {
    border: solid #ffffff; }

.k-checkbox.k-checkbox--success.k-checkbox--solid > input:focus ~ span {
  border: 1px solid transparent !important; }

.k-checkbox.k-checkbox--success.k-checkbox--solid > input:checked ~ span {
  background: #1dc9b7; }

.k-checkbox.k-checkbox--info.k-checkbox--disabled {
  opacity: 0.7; }

.k-checkbox.k-checkbox--info > span {
  border: 1px solid #5578eb; }
  .k-checkbox.k-checkbox--info > span:after {
    border: solid #5578eb; }

.k-checkbox.k-checkbox--info > input:disabled ~ span:after {
  border-color: #5578eb; }

.k-checkbox.k-checkbox--info > input:checked ~ span {
  border: 1px solid #5578eb; }

.k-checkbox.k-checkbox--info.k-checkbox--bold > input:checked ~ span {
  border: 2px solid #5578eb; }

.k-checkbox.k-checkbox--info > input:disabled ~ span {
  opacity: 0.6; }

.k-checkbox.k-checkbox--info.k-checkbox--solid > span {
  background: #5578eb;
  border: 1px solid transparent !important; }
  .k-checkbox.k-checkbox--info.k-checkbox--solid > span:after {
    border: solid #ffffff; }

.k-checkbox.k-checkbox--info.k-checkbox--solid > input:focus ~ span {
  border: 1px solid transparent !important; }

.k-checkbox.k-checkbox--info.k-checkbox--solid > input:checked ~ span {
  background: #5578eb; }

.k-checkbox.k-checkbox--warning.k-checkbox--disabled {
  opacity: 0.7; }

.k-checkbox.k-checkbox--warning > span {
  border: 1px solid #ffb822; }
  .k-checkbox.k-checkbox--warning > span:after {
    border: solid #ffb822; }

.k-checkbox.k-checkbox--warning > input:disabled ~ span:after {
  border-color: #ffb822; }

.k-checkbox.k-checkbox--warning > input:checked ~ span {
  border: 1px solid #ffb822; }

.k-checkbox.k-checkbox--warning.k-checkbox--bold > input:checked ~ span {
  border: 2px solid #ffb822; }

.k-checkbox.k-checkbox--warning > input:disabled ~ span {
  opacity: 0.6; }

.k-checkbox.k-checkbox--warning.k-checkbox--solid > span {
  background: #ffb822;
  border: 1px solid transparent !important; }
  .k-checkbox.k-checkbox--warning.k-checkbox--solid > span:after {
    border: solid #111111; }

.k-checkbox.k-checkbox--warning.k-checkbox--solid > input:focus ~ span {
  border: 1px solid transparent !important; }

.k-checkbox.k-checkbox--warning.k-checkbox--solid > input:checked ~ span {
  background: #ffb822; }

.k-checkbox.k-checkbox--danger.k-checkbox--disabled {
  opacity: 0.7; }

.k-checkbox.k-checkbox--danger > span {
  border: 1px solid #fd397a; }
  .k-checkbox.k-checkbox--danger > span:after {
    border: solid #fd397a; }

.k-checkbox.k-checkbox--danger > input:disabled ~ span:after {
  border-color: #fd397a; }

.k-checkbox.k-checkbox--danger > input:checked ~ span {
  border: 1px solid #fd397a; }

.k-checkbox.k-checkbox--danger.k-checkbox--bold > input:checked ~ span {
  border: 2px solid #fd397a; }

.k-checkbox.k-checkbox--danger > input:disabled ~ span {
  opacity: 0.6; }

.k-checkbox.k-checkbox--danger.k-checkbox--solid > span {
  background: #fd397a;
  border: 1px solid transparent !important; }
  .k-checkbox.k-checkbox--danger.k-checkbox--solid > span:after {
    border: solid #ffffff; }

.k-checkbox.k-checkbox--danger.k-checkbox--solid > input:focus ~ span {
  border: 1px solid transparent !important; }

.k-checkbox.k-checkbox--danger.k-checkbox--solid > input:checked ~ span {
  background: #fd397a; }

```

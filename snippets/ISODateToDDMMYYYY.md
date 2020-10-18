---
title: convertDate
tags: function,intermediate
---

Convert ISO Date to DD-MM-YYYY format

Accept an ISO Date, then take out date, month and year from it, adds 0 if it is single digit number and the returns the date in the format of "DD-MM-YYYY".

```js
const convertDate = (ISODate) => {
  const parsedDate = new Date.parse(ISODate);
  if (parsedDate.toISOString() !== parsedDate)
    throw new BadRequestException("Date validation failed");

  ISODate = new Date(ISODate);

  let year = ISODate.getFullYear();
  let month = ISODate.getMonth() + 1;
  let date = ISODate.getDate();

  if (date < 10) date = `0${date}`;

  if (month < 10) month = `0${month}`;

  return `${date}/${month}/${year}`;
};
```

```js
convertDate("2020-10-18T10:06:43.678Z");
```

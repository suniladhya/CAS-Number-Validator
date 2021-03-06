# CAS-Number-Validator
Oracle PL SQL function to validate CAS Registry Numbers

## What is a CAS Registry Number?
CAS Registry Numbers are universally used to provide a unique, unmistakable identifier for chemical substances. CAS Number is a unique numerical identifier assigned by Chemical Abstracts Service (CAS) to every chemical substance described in the open scientific literature (currently including those described from at least 1957 through the present), including organic and inorganic compounds, minerals, isotopes, alloys and nonstructurable materials (UVCBs, of unknown, variable composition, or biological origin).

A CAS Registry Number itself has no inherent chemical significance but provides an unambiguous way to identify a chemical substance or molecular structure when there are many possible systematic, generic, proprietary or trivial names.

## Usage
The function `f_is_valid_cas_number` takes a CAS Number as the only input parameter, of type `VARCHAR2`, and returns 1 if the input is a valid CAS number and 0 if the input is not a valid CAS Number.

```sql
-- Valid CAS Number for Water, returns 1
SELECT f_is_valid_cas_number('7732-18-5') FROM dual;

-- Invalid syntax, returns 0
SELECT f_is_valid_cas_number('7A2-181-522') FROM dual;

-- Valid syntax but incorrect checksum, returns 0
SELECT f_is_valid_cas_number('1-11-5') FROM dual;
```

In Oracle PL SQL, the function can be used to set a flag as follows:
```sql
  -- Valid CAS Number for Water, sets is_valid_cas_number flag to 1
  is_valid_cas_number NUMBER(1) := f_is_valid_cas_number('7732-18-5');
```


### Useful Links
[CAS Registry Number](http://en.wikipedia.org/wiki/CAS_Registry_Number)

[Chemical Abstracts Service](http://www.cas.org/)

[Chemical Abstracts Service FAQs](http://www.cas.org/about-cas/faqs)




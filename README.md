# Kačių Veislių informacinė sistema
- [ ] Replace "WEB system" with your system name

## Description
- [ ] Provide WEB system description in few sentences - its purpose, users, etc.

- [ ] Sistema pagal paieškos kriterijus parodys tam tikros veisles kačių nuotraukas su jų aprašais, ir suteiks galimybę vartotojui komentuoti ant šių aprašų.

## Entity definition
- [ ] Define the entity ("object" that will be manipulated) of WEB system
- [ ] Entity should have a name
- [ ] Entity should have 3 mandatory attributes:
    - [ ] ID - depending on specific service this could be a number or string
    - [ ] Creation date - (if applicable for specific service) ISO 8601 format date string
    - [ ] Modification date - (if applicable for specific service) ISO 8601 format date string
- [ ] Entity should have at least 5 custom attributes
    - [ ] Each attribute should have a type defined: number, string, ISO 8601 date string, boolean, object, array or other
    - [ ] Each attribute should have restrictions defined: list of constants, or number range, or string length, or string format, or object schema, or array schema or other. For example, you can use `joi` language to define restrictions: https://github.com/hapijs/joi/blob/v13.1.2/API.md
    
- [ ] Comment
    - [ ] commentID (number, 8, mandatory)
    - [ ] catID (string, 8, mandatory)
    - [ ] creationDate (ISO 8601 date string, mandatory)
    - [ ] modificationDate (ISO 8601 date string, mandatory)
    - [ ] commentText (string, 150, mandatory)
    - [ ] username (string, 40, mandatory)
    
- [ ] Cat
    - [ ] catID (string, 8, mandatory)
    - [ ] name (string, 25, mandatory)
    - [ ] altName (string, 100)
    - [ ] lifeSpan (string, 10, mandatory)
    - [ ] childFriendly (integer, 1, mandatory)
    - [ ] dogFriendly (integer, 1, mandatory)
    - [ ] healthIssues(integer, 1, mandatory)

## API definition
- [ ] API methods
    - [ ] get breeds by name GET https://api.thecatapi.com/v1/breeds/search?q={name} {400, 404, 406}
    - [ ] get cat image by id GET https://api.thecatapi.com/v1/images/search?breed_id={catID} {400, 404, 406}
    - [ ] GET komentarai by cat GET /api/komentaras/{catID} {400, 404, 406}
    - [ ] POST komentaras POST /api/komentaras {400, 404}
    - [ ] PUT update komentarą PUT /api/komentaras/{id} {400, 401, 404}
    - [ ] DELETE komentarą  DELETE /api/komentaras/{id} {400, 401, 404}
    - [ ] get a list of cat breeds GET https://api.thecatapi.com/v1/breeds
- [ ] Optionally define additional API methods that WEB system is going to expose
    - [ ] define the below
        - [ ] API should have at least 4 methods
            - [ ] A method to return multiple entities (Array) by ID. This method should support at least one header value to:
                - [ ] Return only entities that match pattern in one of its attributes
                - [ ] Return 10 entities starting provided index
                - [ ] Return sorted entities by one of its attributes (both ascending and descending)
                - [ ] Other (should be approved by Product Owner (PO))
        - [ ] Each method should have HTTP method defined
        - [ ] Each method should have URI defined (use {id} as entity ID placeholder)
        - [ ] Should return all 4xx errors in unified format. Define format using `joi` language
        - [ ] Should return all 5xx errors in unified format. Define format using `joi` language

## UI definition
- [ ] Define the structure of how visually the WEB system is going to look like
- [ ] Should have at least one view defined with https://wireframe.cc (or other wireframe tool):
- [ ] The view should have a title
- [ ] The view should have a description of a service provided by web system
- [ ] The view should include at least 2 UI components:
    - [ ] A component to display multiple entities with all their attribute values visible. It should be posible to remove and edit selected entity.
        - [ ] Depending on chosen header of API method that returns multiple entities, it should be posible to select specific 10 entities starting index, sort entities by attribute, filter entities by attribute pattern, or other (should be approved by Product Owner (PO))
    - [ ] A component to create a new entity/edit existing entity. It should be posbile to create new entity and edit selected entity
        - [ ] Each attribute should have a dedicated editor field: text box for string or number, checkbox or radio buttons for boolean, date picker for date, etc.

- [ ] https://wireframe.cc/ogiSsA

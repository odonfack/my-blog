---
headless: true

---
    {{ with .Params.image }}
        {{ $imageResource := ($.Site.GetPage "section" "uploads").Resources.GetMatch (strings.TrimPrefix "/uploads/" . ) }}
        {{ $resized := $imageResource.Fill "200x200" }}
        <img src="{{ $resized.RelPermalink }}" />
    {{ end }}
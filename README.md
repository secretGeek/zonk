# zonk

Zonk is a system for embedding queries and other interactive components in markdown documents.

It could be used in an interactive wiki, or in a system that generates static html from markdown documents, or in other as yet unimagined places.

## zonk is an open standard

Zonk is an idea and there is an open standard for zonk.

Implementations of the zonk standard may not implement every fragment of the standard. They may also implement competing standards.

## the zonk standard

### `zs:lst` zonk implementors maintain a list

For every implementation: the implementer(s) should maintain a table of information that indicates which fragments of the standard are implemented. Or if an alternative of the standard is implement for a given fragment, that should also be listed.

A global list of implementers and which fragments of the standard are implemented should also be maintained somewhere close to here.

Each fragment of the standard has an identifier like this: `zs:aaa.bbb.ccc` where `aaa.bbb.ccc` is a set of one or more alphanumeric codes, separated by dots.

### `zs:blk` zonk is made out of blocks

When writing a markdown document, you can include zonk blocks (hereafter referred to as "zonks" plural or "zonk" singular).

### `zs:blk.syn` zonks have a basic syntax

A zonk has this syntax:

`{type:content:}`

(Where `type` is a `zonk-type-identifier` and `content` is the content.)

In English:

> A zonk starts with an opening curly bracket (`{`) and is immediately following by a `zonk-type-identifier`, then a colon.
> Next comes the content of the zonk. The content may be zero characters long, or long. It can contain anything. But it cannot contains a colon followed by a closing curly bracket. The zonk ends with a colon (`:`) and a closing curly bracket (`}`).

`draft` `todo` This regular expression should find zonks in a document:

`draft` `todo` This regular expression should find zonks (and isolate their types and content into named groups) in a document:

`todo` name the groups for `zonk-type-identifier` and `zonk-content`

`draft` A zonk on its own should match this regular expression


### `zs:blk.syn.typ.ids` zonk type identifiers are simple strings

A `zonk-type identifier` is a short and meanigful name that follows a few rules.

- It is a lower-case string.
- It starts with a letter a-z
- It is composed of letters, numbers, underscore, hyphen, dots.


`draft` This regular expression should match a zonk type identifier on its own:

    ^[a-z][a-z0-9._\-]*$

### `zs:blk.syn.typ.ids.irn` zonk type identifiers don't include colons.

The iron-law of zonk type identifiers is that they're at least one character long and don't include colons.

This makes finding them a "regular" parsing problem and requires no escape rules.

`TODO` A regular expression for validating the iron-law of zonk identifier.

`draft` This regular expression should match a zonk type identifier on its own, if it obeys the iron-law of zonk identifiers.

    ^[^:]+$


### `zs:blk.syn.cnt` zonk content doesn't include the substring ":}"

You can't nest zonks. (Zonks are *regular*). This takes away a lot of complexity that would arise for people writing markdown that includes zonk blocks.

(A different set of standard fragments could be written to cover "nestable" zonks. But that is not *this* set of standard fragments.)






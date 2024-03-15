# hugo bug(?)

tl;dr when you run this example instead of contents in your variable, you get HAHAHUGOSHORTCOD /  HAHAHUGOSHORTCODE text (see index.md in content dir and asdf shortcode and link render hook in layout).

to get this text you have to do some string splitting trick, or at least this is what worked for me.

The HAHAHUGOSHORTCOD… text is apparently also received by `strings.FindRE` function as well.

Workaround is to use %% tags.

Given how tricky it is to find this behavior, I can't tell if it's a bug or a feature.

## Update

[It's a feature apparently…](https://discourse.gohugo.io/t/destination-from-rel-or-relref-does-has-unexpect-prefix/42848).

This unique fragment is then stringreplaced, which is why printing full text works, but not parsing it…

Give me a break plz.
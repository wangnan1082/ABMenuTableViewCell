# ABMenuTableViewCell
=====================

Solution for using your own custom view as a menu in an UITableView’s “swipe to delete”-menu gesture.

![Screenshot](https://github.com/alexbumbu/ABMenuTableViewCell/blob/master/sample_1.png?raw=true)

![Screenshot](https://github.com/alexbumbu/ABMenuTableViewCell/blob/master/sample_2.png?raw=true)

## Integration

You just need to replace UITableViewCell with ABMenuTableViewCell and assign your custom menu view to rightMenuView property and you're ready to go! You can take a look at the following snippet for details.

```objective-c
- (UITableViewCell*)tableView:(UITableView *)tableView cellForRowAtIndexPath:(NSIndexPath *)indexPath {
    static NSString *identifier = @"ABMenuTableViewCell";
    ABMenuTableViewCell *cell = (ABMenuTableViewCell*)[tableView cellForRowAtIndexPath:indexPath];

    if (!cell) {
        cell = [[ABMenuTableViewCell alloc] initWithStyle:UITableViewCellStyleDefault reuseIdentifier:identifier];
    }
    
    // use your own custom menu view
    UIView *menuView = [[UIView alloc] initWithFrame:CGRectMake(.0, .0, 160.0, 44.0)];
    menuView.backgroundColor = [UIColor redColor];

    cell.rightMenuView = menuView;
    cell.textLabel.text = @"Lorem ipsum dolor sit amet";

    return cell;
}
```
